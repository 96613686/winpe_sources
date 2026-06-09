# IMSAdminBaseW_R_GetData_Thunk

- ea: `0x180001f30`
- end: `0x1800020dc`
- name: `IMSAdminBaseW_R_GetData_Thunk`
- size: `428`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task`

## callees

- `0x180001124`
- `0x180001f30`
- `0x1800031f4`
- `0x180003e3c`
- `0x180004808`
- `0x180009010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180001f7f`
- `KERNEL32!LocalAlloc` at `0x180001f7f`
- `KERNEL32!LocalFree` at `0x18000207f`
- `KERNEL32!LocalFree` at `0x18000207f`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180001fe5`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180001fe5`
- `ole32!CoTaskMemFree` at `0x180002096`
- `ole32!CoTaskMemFree` at `0x180002096`

## pseudocode

```c
void __fastcall IMSAdminBaseW_R_GetData_Thunk(__int64 a1)
{
  __int64 v1; // r14
  __int64 v2; // rbp
  LPVOID *v3; // r13
  __int64 v4; // rdi
  struct IUnknown *v5; // r15
  SIZE_T v6; // rdx
  HLOCAL v7; // rax
  _QWORD *v8; // rbx
  void *v9; // r12
  int v10; // edi
  __int64 v11; // r8
  __int64 v12; // rdx
  volatile signed __int32 *v13; // rsi
  struct ADM_SECURE_DATA *v14; // rax
  __int64 (__fastcall ***v15)(_QWORD, LPVOID *, _QWORD, _QWORD, _DWORD); // rcx
  int v16; // eax
  void *v17; // rcx
  unsigned int ClientLocalFlag; // [rsp+70h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+10h] BYREF
  __int64 v20; // [rsp+80h] [rbp+18h]

  v1 = *(_QWORD *)(a1 + 136);
  pv = 0;
  v2 = *(_QWORD *)(v1 + 24);
  v3 = *(LPVOID **)(v1 + 40);
  v4 = *(_QWORD *)(v1 + 32);
  v5 = *(struct IUnknown **)v1;
  v6 = *(unsigned int *)(v2 + 16);
  v20 = *(_QWORD *)(v1 + 16);
  ClientLocalFlag = *(_DWORD *)(v1 + 8);
  v7 = LocalAlloc(0x40u, v6);
  v8 = (_QWORD *)(v2 + 24);
  v9 = v7;
  if ( v7 )
  {
    v11 = v20;
    v12 = ClientLocalFlag;
    *v8 = v7;
    v13 = 0;
    v10 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64, __int64))v5->lpVtbl[3].AddRef)(
            v5,
            v12,
            v11,
            v2,
            v4);
    if ( v10 >= 0 )
    {
      if ( (*(_BYTE *)(v2 + 4) & 4) != 0
        && ((ClientLocalFlag = 0, I_RpcBindingIsClientLocal(0, &ClientLocalFlag)) || !ClientLocalFlag) )
      {
        v14 = ADM_SECURE_DATA::FindAndReferenceServerSecureData(v5, 1);
        v13 = (volatile signed __int32 *)v14;
        if ( !v14 )
        {
          v10 = -2146646010;
          *v8 = 0;
          goto LABEL_16;
        }
        v15 = (__int64 (__fastcall ***)(_QWORD, LPVOID *, _QWORD, _QWORD, _DWORD))*((_QWORD *)v14 + 6);
        if ( !v15 )
        {
          v10 = -2146646010;
          *v8 = 0;
LABEL_14:
          if ( _InterlockedExchangeAdd(v13 + 6, 0xFFFFFFFF) == 1 )
          {
            ADM_SECURE_DATA::~ADM_SECURE_DATA((ADM_SECURE_DATA *)v13);
            operator delete((void *)v13);
          }
LABEL_16:
          LocalFree(v9);
          if ( v10 >= 0 )
            goto LABEL_19;
          goto LABEL_17;
        }
        v16 = (**v15)(v15, &pv, *v8, *(unsigned int *)(v2 + 16), 0);
      }
      else
      {
        v16 = IISCryptoCreateCleartextBlob(&pv, *v8, *(unsigned int *)(v2 + 16));
      }
      v10 = v16;
      if ( v16 >= 0 )
        *v3 = pv;
    }
    *v8 = 0;
    if ( !v13 )
      goto LABEL_16;
    goto LABEL_14;
  }
  v10 = -2147024888;
  *v8 = 0;
LABEL_17:
  v17 = pv;
  if ( pv )
  {
    *(_BYTE *)pv = 88;
    CoTaskMemFree(v17);
  }
LABEL_19:
  *(_DWORD *)(v1 + 48) = v10;
}

```

## disassembly

```asm
0x180001f30  mov     [rsp+arg_18], rbx
0x180001f35  push    rbp
0x180001f36  push    rsi
0x180001f37  push    rdi
0x180001f38  push    r12
0x180001f3a  push    r13
0x180001f3c  push    r14
0x180001f3e  push    r15
0x180001f40  sub     rsp, 30h
0x180001f44  mov     r14, [rcx+88h]
0x180001f4b  mov     ecx, 40h ; '@'; uFlags
0x180001f50  mov     [rsp+68h+pv], 0
0x180001f59  mov     rax, [r14+10h]
0x180001f5d  mov     rbp, [r14+18h]
0x180001f61  mov     r13, [r14+28h]
0x180001f65  mov     rdi, [r14+20h]
0x180001f69  mov     r15, [r14]
0x180001f6c  mov     edx, [rbp+10h]; uBytes
0x180001f6f  mov     [rsp+68h+arg_10], rax
0x180001f77  mov     eax, [r14+8]
0x180001f7b  mov     [rsp+68h+ClientLocalFlag], eax
0x180001f7f  call    cs:__imp_LocalAlloc
0x180001f85  lea     rbx, [rbp+18h]
0x180001f89  mov     r12, rax
0x180001f8c  test    rax, rax
0x180001f8f  jnz     short loc_180001F9E
0x180001f91  mov     edi, 80070008h
0x180001f96  mov     [rbx], rax
0x180001f99  jmp     loc_180002089
0x180001f9e  mov     r8, [rsp+68h+arg_10]
0x180001fa6  mov     r9, rbp
0x180001fa9  mov     edx, [rsp+68h+ClientLocalFlag]
0x180001fad  mov     rcx, r15
0x180001fb0  mov     [rbx], r12
0x180001fb3  xor     esi, esi
0x180001fb5  mov     rax, [r15]
0x180001fb8  mov     [rsp+68h+var_48], rdi
0x180001fbd  mov     rax, [rax+50h]
0x180001fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fc6  mov     edi, eax
0x180001fc8  test    eax, eax
0x180001fca  js      loc_180002053
0x180001fd0  test    byte ptr [rbp+4], 4
0x180001fd4  jz      loc_1800020C6
0x180001fda  lea     rdx, [rsp+68h+ClientLocalFlag]; ClientLocalFlag
0x180001fdf  mov     [rsp+68h+ClientLocalFlag], esi
0x180001fe3  xor     ecx, ecx; BindingHandle
0x180001fe5  call    cs:__imp_I_RpcBindingIsClientLocal
0x180001feb  test    eax, eax
0x180001fed  jnz     short loc_180001FF9
0x180001fef  cmp     [rsp+68h+ClientLocalFlag], esi
0x180001ff3  jnz     loc_1800020C6
0x180001ff9  mov     edx, 1; int
0x180001ffe  mov     rcx, r15; struct IUnknown *
0x180002001  call    ?FindAndReferenceServerSecureData@ADM_SECURE_DATA@@SAPEAV1@PEAUIUnknown@@H@Z; ADM_SECURE_DATA::FindAndReferenceServerSecureData(IUnknown *,int)
0x180002006  mov     rsi, rax
0x180002009  test    rax, rax
0x18000200c  jnz     short loc_180002018
0x18000200e  mov     edi, 800CC806h
0x180002013  mov     [rbx], rax
0x180002016  jmp     short loc_18000207C
0x180002018  mov     rcx, [rax+30h]
0x18000201c  test    rcx, rcx
0x18000201f  jz      loc_1800020B8
0x180002025  mov     rax, [rcx]
0x180002028  lea     rdx, [rsp+68h+pv]
0x18000202d  mov     r9d, [rbp+10h]
0x180002031  mov     r8, [rbx]
0x180002034  mov     dword ptr [rsp+68h+var_48], 0
0x18000203c  mov     rax, [rax]
0x18000203f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002044  mov     edi, eax
0x180002046  test    eax, eax
0x180002048  js      short loc_180002053
0x18000204a  mov     rax, [rsp+68h+pv]
0x18000204f  mov     [r13+0], rax
0x180002053  mov     qword ptr [rbx], 0
0x18000205a  test    rsi, rsi
0x18000205d  jz      short loc_18000207C
0x18000205f  or      eax, 0FFFFFFFFh
0x180002062  lock xadd [rsi+18h], eax
0x180002067  cmp     eax, 1
0x18000206a  jnz     short loc_18000207C
0x18000206c  mov     rcx, rsi; this
0x18000206f  call    ??1ADM_SECURE_DATA@@QEAA@XZ; ADM_SECURE_DATA::~ADM_SECURE_DATA(void)
0x180002074  mov     rcx, rsi; Block
0x180002077  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000207c  mov     rcx, r12; hMem
0x18000207f  call    cs:__imp_LocalFree
0x180002085  test    edi, edi
0x180002087  jns     short loc_18000209C
0x180002089  mov     rcx, [rsp+68h+pv]; pv
0x18000208e  test    rcx, rcx
0x180002091  jz      short loc_18000209C
0x180002093  mov     byte ptr [rcx], 58h ; 'X'
0x180002096  call    cs:__imp_CoTaskMemFree
0x18000209c  mov     rbx, [rsp+68h+arg_18]
0x1800020a4  mov     [r14+30h], edi
0x1800020a8  add     rsp, 30h
0x1800020ac  pop     r15
0x1800020ae  pop     r14
0x1800020b0  pop     r13
0x1800020b2  pop     r12
0x1800020b4  pop     rdi
0x1800020b5  pop     rsi
0x1800020b6  pop     rbp
0x1800020b7  retn
0x1800020b8  mov     edi, 800CC806h
0x1800020bd  mov     qword ptr [rbx], 0
0x1800020c4  jmp     short loc_18000205F
0x1800020c6  mov     r8d, [rbp+10h]
0x1800020ca  lea     rcx, [rsp+68h+pv]
0x1800020cf  mov     rdx, [rbx]
0x1800020d2  call    IISCryptoCreateCleartextBlob
0x1800020d7  jmp     loc_180002044
```
