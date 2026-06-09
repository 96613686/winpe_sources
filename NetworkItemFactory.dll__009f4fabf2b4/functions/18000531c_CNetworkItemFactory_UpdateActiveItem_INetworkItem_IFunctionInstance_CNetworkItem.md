# CNetworkItemFactory::_UpdateActiveItem(INetworkItem *,IFunctionInstance *,CNetworkItem * *)

- ea: `0x18000531c`
- end: `0x180005424`
- name: `?_UpdateActiveItem@CNetworkItemFactory@@AEAAJPEAUINetworkItem@@PEAUIFunctionInstance@@PEAPEAVCNetworkItem@@@Z`
- size: `264`
- prototype: `__int64 __fastcall(CProfileCache **this, struct INetworkItem *, struct IFunctionInstance *, struct CNetworkItem **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000488c`

## callees

- `0x180003d28`
- `0x18000442c`
- `0x18000531c`
- `0x1800082bc`
- `0x18000b010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800053ea`
- `ole32!CoTaskMemFree` at `0x180005409`
- `ole32!CoTaskMemFree` at `0x1800053ea`
- `ole32!CoTaskMemFree` at `0x180005409`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory::_UpdateActiveItem(
        CProfileCache **this,
        struct INetworkItem *a2,
        struct IFunctionInstance *a3,
        struct CNetworkItem **a4)
{
  __int64 v4; // rax
  signed int ComputerNameAlloc; // edi
  __int64 v10; // rax
  int v11; // ebx
  LPVOID v13[5]; // [rsp+20h] [rbp-28h] BYREF
  int v14; // [rsp+58h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+68h] [rbp+20h] BYREF

  v4 = *(_QWORD *)a2;
  *a4 = 0;
  v13[0] = 0;
  ComputerNameAlloc = (*(__int64 (__fastcall **)(struct INetworkItem *, LPVOID *))(v4 + 32))(a2, v13);
  if ( ComputerNameAlloc >= 0 )
  {
    if ( (unsigned int)LKRhash::CLKRHashTable::DeleteKey(this[10], v13[0]) )
    {
      ComputerNameAlloc = -2147467259;
    }
    else
    {
      v10 = *(_QWORD *)a2;
      v14 = 0;
      if ( (*(int (__fastcall **)(struct INetworkItem *, int *))(v10 + 48))(a2, &v14) < 0
        || !v14
        || (pv = 0,
            ComputerNameAlloc = CNetworkItemFactory::_GetComputerNameAlloc(a2, (unsigned __int16 **)&pv),
            ComputerNameAlloc >= 0)
        && (v11 = LKRhash::CLKRHashTable::DeleteKey(this[11], pv),
            ComputerNameAlloc = v11 != 0 ? 0x80004005 : 0,
            CoTaskMemFree(pv),
            !v11) )
      {
        ComputerNameAlloc = CNetworkItemFactory::_AddNewItem(this, a3, a4);
      }
    }
    CoTaskMemFree(v13[0]);
  }
  return (unsigned int)ComputerNameAlloc;
}

```

## disassembly

```asm
0x18000531c  mov     r11, rsp
0x18000531f  mov     [r11+8], rbx
0x180005323  mov     [r11+18h], rbp
0x180005327  push    rsi
0x180005328  push    rdi
0x180005329  push    r14
0x18000532b  sub     rsp, 30h
0x18000532f  mov     rax, [rdx]
0x180005332  mov     rbx, rdx
0x180005335  mov     rsi, rcx
0x180005338  mov     qword ptr [r9], 0
0x18000533f  lea     rdx, [r11-28h]
0x180005343  mov     qword ptr [r11-28h], 0
0x18000534b  mov     rcx, rbx
0x18000534e  mov     r14, r9
0x180005351  mov     rax, [rax+20h]
0x180005355  mov     rbp, r8
0x180005358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000535d  mov     edi, eax
0x18000535f  test    eax, eax
0x180005361  js      loc_18000540F
0x180005367  mov     rdx, [rsp+48h+var_28]
0x18000536c  mov     rcx, [rsi+50h]
0x180005370  call    ?DeleteKey@CLKRHashTable@LKRhash@@QEAA?AW4LK_RETCODE@2@_K@Z; LKRhash::CLKRHashTable::DeleteKey(unsigned __int64)
0x180005375  test    eax, eax
0x180005377  jz      short loc_180005383
0x180005379  mov     edi, 80004005h
0x18000537e  jmp     loc_180005404
0x180005383  mov     rax, [rbx]
0x180005386  lea     rdx, [rsp+48h+arg_8]
0x18000538b  mov     rcx, rbx
0x18000538e  mov     [rsp+48h+arg_8], 0
0x180005396  mov     rax, [rax+30h]
0x18000539a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000539f  test    eax, eax
0x1800053a1  js      short loc_1800053F4
0x1800053a3  cmp     [rsp+48h+arg_8], 0
0x1800053a8  jz      short loc_1800053F4
0x1800053aa  lea     rdx, [rsp+48h+pv]; unsigned __int16 **
0x1800053af  mov     [rsp+48h+pv], 0
0x1800053b8  mov     rcx, rbx; struct INetworkItem *
0x1800053bb  call    ?_GetComputerNameAlloc@CNetworkItemFactory@@CAJPEAUINetworkItem@@PEAPEAG@Z; CNetworkItemFactory::_GetComputerNameAlloc(INetworkItem *,ushort * *)
0x1800053c0  mov     edi, eax
0x1800053c2  test    eax, eax
0x1800053c4  js      short loc_180005404
0x1800053c6  mov     rdx, [rsp+48h+pv]
0x1800053cb  mov     rcx, [rsi+58h]
0x1800053cf  call    ?DeleteKey@CLKRHashTable@LKRhash@@QEAA?AW4LK_RETCODE@2@_K@Z; LKRhash::CLKRHashTable::DeleteKey(unsigned __int64)
0x1800053d4  mov     rcx, [rsp+48h+pv]; pv
0x1800053d9  xor     edx, edx
0x1800053db  sub     edx, eax
0x1800053dd  mov     edi, 80004005h
0x1800053e2  neg     edx
0x1800053e4  mov     ebx, eax
0x1800053e6  sbb     edx, edx
0x1800053e8  and     edi, edx
0x1800053ea  call    cs:__imp_CoTaskMemFree
0x1800053f0  test    ebx, ebx
0x1800053f2  jnz     short loc_180005404
0x1800053f4  mov     r8, r14; struct CNetworkItem **
0x1800053f7  mov     rdx, rbp; struct IFunctionInstance *
0x1800053fa  mov     rcx, rsi; this
0x1800053fd  call    ?_AddNewItem@CNetworkItemFactory@@AEAAJPEAUIFunctionInstance@@PEAPEAVCNetworkItem@@@Z; CNetworkItemFactory::_AddNewItem(IFunctionInstance *,CNetworkItem * *)
0x180005402  mov     edi, eax
0x180005404  mov     rcx, [rsp+48h+var_28]; pv
0x180005409  call    cs:__imp_CoTaskMemFree
0x18000540f  mov     rbx, [rsp+48h+arg_0]
0x180005414  mov     eax, edi
0x180005416  mov     rbp, [rsp+48h+arg_10]
0x18000541b  add     rsp, 30h
0x18000541f  pop     r14
0x180005421  pop     rdi
0x180005422  pop     rsi
0x180005423  retn
```
