# CNetworkItemFactory::_HandleDeviceRemove(IFunctionInstance *)

- ea: `0x1800049f4`
- end: `0x180004b99`
- name: `?_HandleDeviceRemove@CNetworkItemFactory@@AEAAJPEAUIFunctionInstance@@@Z`
- size: `421`
- prototype: `__int64 __fastcall(CNetworkItemFactory *__hidden this, struct IFunctionInstance *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800037f8`

## callees

- `0x18000442c`
- `0x1800049f4`
- `0x180004fb0`
- `0x1800058c4`
- `0x1800070f4`
- `0x1800082bc`
- `0x180008354`
- `0x18000b010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180004b12`
- `ole32!CoTaskMemFree` at `0x180004b66`
- `ole32!CoTaskMemFree` at `0x180004b80`
- `ole32!CoTaskMemFree` at `0x180004b12`
- `ole32!CoTaskMemFree` at `0x180004b66`
- `ole32!CoTaskMemFree` at `0x180004b80`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory::_HandleDeviceRemove(CNetworkItemFactory *this, struct IFunctionInstance *a2)
{
  signed int ComputerNameAlloc; // edi
  __int64 v4; // r8
  void *v5; // r14
  struct INetworkItem **v6; // rsi
  __int64 v7; // r8
  void *v8; // rdi
  int v9; // ebx
  void *lpMem; // [rsp+58h] [rbp+38h] BYREF
  LPVOID v12; // [rsp+60h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+68h] [rbp+48h] BYREF

  v12 = 0;
  ComputerNameAlloc = ((__int64 (__fastcall *)(struct IFunctionInstance *, LPVOID *))a2->lpVtbl->GetID)(a2, &v12);
  if ( ComputerNameAlloc >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v4, v12);
    }
    lpMem = 0;
    if ( (unsigned int)LKRhash::CLKRHashTable::FindKey(*((_QWORD *)this + 10), v12, &lpMem) )
    {
      ComputerNameAlloc = -2147467259;
    }
    else
    {
      v5 = lpMem;
      v6 = (struct INetworkItem **)((char *)lpMem + 8);
      if ( (unsigned int)LKRhash::CLKRHashTable::DeleteKey(*((_QWORD *)this + 10), v12) )
      {
        ComputerNameAlloc = -2147467259;
      }
      else
      {
        ComputerNameAlloc = 0;
        LODWORD(lpMem) = 0;
        (*(void (__fastcall **)(struct INetworkItem *, void **))(*(_QWORD *)*v6 + 48LL))(*v6, &lpMem);
        if ( !(_DWORD)lpMem )
          goto LABEL_15;
        pv = 0;
        ComputerNameAlloc = CNetworkItemFactory::_GetComputerNameAlloc(*v6, (unsigned __int16 **)&pv);
        if ( ComputerNameAlloc >= 0 )
        {
          v8 = pv;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v7, pv);
          }
          v9 = LKRhash::CLKRHashTable::DeleteKey(*((_QWORD *)this + 11), v8);
          CoTaskMemFree(v8);
          ComputerNameAlloc = v9 != 0 ? 0x80004005 : 0;
          if ( !v9 )
LABEL_15:
            CNetworkItemFactory::_SendNotification(this, 4, *v6);
        }
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 4, 0xFFFFFFFF) == 1 && v5 )
      {
        (*(void (__fastcall **)(struct INetworkItem *))(*(_QWORD *)*v6 + 16LL))(*v6);
        CoTaskMemFree(*(LPVOID *)v5);
        operator delete(v5);
      }
    }
    CoTaskMemFree(v12);
  }
  return (unsigned int)ComputerNameAlloc;
}

```

## disassembly

```asm
0x1800049f4  mov     [rsp-28h+arg_0], rbx
0x1800049f9  push    rbp
0x1800049fa  push    rsi
0x1800049fb  push    rdi
0x1800049fc  push    r14
0x1800049fe  push    r15
0x180004a00  mov     rbp, rsp
0x180004a03  sub     rsp, 20h
0x180004a07  mov     r8, rdx
0x180004a0a  mov     r15, rcx
0x180004a0d  mov     [rbp+arg_10], 0
0x180004a15  mov     rax, [rdx]
0x180004a18  lea     rdx, [rbp+arg_10]
0x180004a1c  mov     rcx, r8
0x180004a1f  mov     rax, [rax+20h]
0x180004a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a28  mov     edi, eax
0x180004a2a  test    eax, eax
0x180004a2c  js      loc_180004B86
0x180004a32  lea     rbx, WPP_GLOBAL_Control
0x180004a39  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a40  cmp     rcx, rbx
0x180004a43  jz      short loc_180004A63
0x180004a45  cmp     byte ptr [rcx+19h], 5
0x180004a49  jb      short loc_180004A63
0x180004a4b  test    byte ptr [rcx+1Ch], 2
0x180004a4f  jz      short loc_180004A63
0x180004a51  mov     edx, 0Ch
0x180004a56  mov     r9, [rbp+arg_10]
0x180004a5a  mov     rcx, [rcx+10h]
0x180004a5e  call    WPP_SF_S
0x180004a63  mov     [rbp+lpMem], 0
0x180004a6b  lea     r8, [rbp+lpMem]
0x180004a6f  mov     rdx, [rbp+arg_10]
0x180004a73  mov     rcx, [r15+50h]
0x180004a77  call    ?FindKey@CLKRHashTable@LKRhash@@QEBA?AW4LK_RETCODE@2@_KPEAPEBX@Z; LKRhash::CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180004a7c  test    eax, eax
0x180004a7e  jnz     loc_180004B77
0x180004a84  mov     r14, [rbp+lpMem]
0x180004a88  mov     rdx, [rbp+arg_10]
0x180004a8c  mov     rcx, [r15+50h]
0x180004a90  call    ?DeleteKey@CLKRHashTable@LKRhash@@QEAA?AW4LK_RETCODE@2@_K@Z; LKRhash::CLKRHashTable::DeleteKey(unsigned __int64)
0x180004a95  lea     rsi, [r14+8]
0x180004a99  test    eax, eax
0x180004a9b  jnz     loc_180004B3C
0x180004aa1  xor     edi, edi
0x180004aa3  mov     dword ptr [rbp+lpMem], edi
0x180004aa6  mov     rcx, [rsi]
0x180004aa9  mov     rax, [rcx]
0x180004aac  lea     rdx, [rbp+lpMem]
0x180004ab0  mov     rax, [rax+30h]
0x180004ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ab9  cmp     dword ptr [rbp+lpMem], edi
0x180004abc  jz      short loc_180004B2A
0x180004abe  mov     [rbp+pv], rdi
0x180004ac2  lea     rdx, [rbp+pv]; unsigned __int16 **
0x180004ac6  mov     rcx, [rsi]; struct INetworkItem *
0x180004ac9  call    ?_GetComputerNameAlloc@CNetworkItemFactory@@CAJPEAUINetworkItem@@PEAPEAG@Z; CNetworkItemFactory::_GetComputerNameAlloc(INetworkItem *,ushort * *)
0x180004ace  mov     edi, eax
0x180004ad0  test    eax, eax
0x180004ad2  js      short loc_180004B41
0x180004ad4  mov     rdi, [rbp+pv]
0x180004ad8  mov     rcx, cs:WPP_GLOBAL_Control
0x180004adf  cmp     rcx, rbx
0x180004ae2  jz      short loc_180004B01
0x180004ae4  cmp     byte ptr [rcx+19h], 5
0x180004ae8  jb      short loc_180004B01
0x180004aea  test    byte ptr [rcx+1Ch], 2
0x180004aee  jz      short loc_180004B01
0x180004af0  mov     edx, 0Dh
0x180004af5  mov     r9, rdi
0x180004af8  mov     rcx, [rcx+10h]
0x180004afc  call    WPP_SF_S
0x180004b01  mov     rdx, rdi
0x180004b04  mov     rcx, [r15+58h]
0x180004b08  call    ?DeleteKey@CLKRHashTable@LKRhash@@QEAA?AW4LK_RETCODE@2@_K@Z; LKRhash::CLKRHashTable::DeleteKey(unsigned __int64)
0x180004b0d  mov     ebx, eax
0x180004b0f  mov     rcx, rdi; pv
0x180004b12  call    cs:__imp_CoTaskMemFree
0x180004b18  xor     ecx, ecx
0x180004b1a  sub     ecx, ebx
0x180004b1c  neg     ecx
0x180004b1e  sbb     edi, edi
0x180004b20  and     edi, 80004005h
0x180004b26  test    ebx, ebx
0x180004b28  jnz     short loc_180004B41
0x180004b2a  mov     r8, [rsi]; struct INetworkItem *
0x180004b2d  mov     edx, 4; int
0x180004b32  mov     rcx, r15; this
0x180004b35  call    ?_SendNotification@CNetworkItemFactory@@AEAAJJPEAUINetworkItem@@@Z; CNetworkItemFactory::_SendNotification(long,INetworkItem *)
0x180004b3a  jmp     short loc_180004B41
0x180004b3c  mov     edi, 80004005h
0x180004b41  or      eax, 0FFFFFFFFh
0x180004b44  lock xadd [r14+10h], eax
0x180004b4a  cmp     eax, 1
0x180004b4d  jnz     short loc_180004B7C
0x180004b4f  test    r14, r14
0x180004b52  jz      short loc_180004B7C
0x180004b54  mov     rcx, [rsi]
0x180004b57  mov     rax, [rcx]
0x180004b5a  mov     rax, [rax+10h]
0x180004b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b63  mov     rcx, [r14]; pv
0x180004b66  call    cs:__imp_CoTaskMemFree
0x180004b6c  nop
0x180004b6d  mov     rcx, r14; lpMem
0x180004b70  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004b75  jmp     short loc_180004B7C
0x180004b77  mov     edi, 80004005h
0x180004b7c  mov     rcx, [rbp+arg_10]; pv
0x180004b80  call    cs:__imp_CoTaskMemFree
0x180004b86  mov     eax, edi
0x180004b88  mov     rbx, [rsp+20h+arg_0]
0x180004b8d  add     rsp, 20h
0x180004b91  pop     r15
0x180004b93  pop     r14
0x180004b95  pop     rdi
0x180004b96  pop     rsi
0x180004b97  pop     rbp
0x180004b98  retn
```
