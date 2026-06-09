# IMSAdminBaseW_R_EnumData_Thunk

- ea: `0x180001ce0`
- end: `0x180001eb4`
- name: `IMSAdminBaseW_R_EnumData_Thunk`
- size: `468`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task`

## callees

- `0x180001124`
- `0x180001ce0`
- `0x1800031f4`
- `0x180003e3c`
- `0x180004808`
- `0x180009010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180001d3b`
- `KERNEL32!LocalAlloc` at `0x180001d3b`
- `KERNEL32!LocalFree` at `0x180001e58`
- `KERNEL32!LocalFree` at `0x180001e58`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180001db5`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180001db5`
- `ole32!CoTaskMemFree` at `0x180001e72`
- `ole32!CoTaskMemFree` at `0x180001e72`

## pseudocode

```c
void __fastcall IMSAdminBaseW_R_EnumData_Thunk(__int64 a1)
{
  __int64 v1; // r14
  __int64 v2; // rbp
  LPVOID *v3; // r13
  __int64 v4; // rdi
  struct IUnknown *v5; // r15
  SIZE_T v6; // rdx
  HLOCAL v7; // rax
  const void **v8; // rbx
  void *v9; // r12
  int v10; // edi
  unsigned int v11; // ecx
  __int64 v12; // r8
  volatile signed __int32 *v13; // rsi
  __int64 v14; // rdx
  struct ADM_SECURE_DATA *v15; // rax
  __int64 (__fastcall ***v16)(_QWORD, LPVOID *, const void *, _QWORD, _DWORD); // rcx
  int v17; // eax
  void *v18; // rcx
  unsigned int ClientLocalFlag; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v20; // [rsp+98h] [rbp+10h]
  LPVOID pv; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v22; // [rsp+A8h] [rbp+20h]

  v1 = *(_QWORD *)(a1 + 136);
  pv = 0;
  v2 = *(_QWORD *)(v1 + 24);
  v3 = *(LPVOID **)(v1 + 48);
  v4 = *(_QWORD *)(v1 + 40);
  v5 = *(struct IUnknown **)v1;
  v6 = *(unsigned int *)(v2 + 16);
  ClientLocalFlag = *(_DWORD *)(v1 + 32);
  v22 = *(_QWORD *)(v1 + 16);
  v20 = *(_DWORD *)(v1 + 8);
  v7 = LocalAlloc(0x40u, v6);
  v8 = (const void **)(v2 + 24);
  v9 = v7;
  if ( v7 )
  {
    v11 = ClientLocalFlag;
    v12 = v22;
    v13 = 0;
    v14 = v20;
    *v8 = v7;
    v10 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64, unsigned int, __int64))v5->lpVtbl[4].QueryInterface)(
            v5,
            v14,
            v12,
            v2,
            v11,
            v4);
    if ( v10 >= 0 )
    {
      if ( (*(_BYTE *)(v2 + 4) & 4) != 0
        && ((ClientLocalFlag = 0, I_RpcBindingIsClientLocal(0, &ClientLocalFlag)) || !ClientLocalFlag) )
      {
        v15 = ADM_SECURE_DATA::FindAndReferenceServerSecureData(v5, 1);
        v13 = (volatile signed __int32 *)v15;
        if ( !v15 )
        {
          v10 = -2146646010;
          *v8 = 0;
          goto LABEL_16;
        }
        v16 = (__int64 (__fastcall ***)(_QWORD, LPVOID *, const void *, _QWORD, _DWORD))*((_QWORD *)v15 + 6);
        if ( !v16 )
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
        v17 = (**v16)(v16, &pv, *v8, *(unsigned int *)(v2 + 16), 0);
      }
      else
      {
        v17 = IISCryptoCreateCleartextBlob(&pv, *v8, *(_DWORD *)(v2 + 16));
      }
      v10 = v17;
      if ( v17 >= 0 )
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
  v18 = pv;
  if ( pv )
  {
    *(_BYTE *)pv = 88;
    CoTaskMemFree(v18);
  }
LABEL_19:
  *(_DWORD *)(v1 + 56) = v10;
}

```

## disassembly

```asm
0x180001ce0  mov     r11, rsp
0x180001ce3  push    rbx
0x180001ce4  push    rbp
0x180001ce5  push    rsi
0x180001ce6  push    rdi
0x180001ce7  push    r12
0x180001ce9  push    r13
0x180001ceb  push    r14
0x180001ced  push    r15
0x180001cef  sub     rsp, 48h
0x180001cf3  mov     r14, [rcx+88h]
0x180001cfa  mov     ecx, 40h ; '@'; uFlags
0x180001cff  mov     qword ptr [r11+18h], 0
0x180001d07  mov     eax, [r14+20h]
0x180001d0b  mov     rbp, [r14+18h]
0x180001d0f  mov     r13, [r14+30h]
0x180001d13  mov     rdi, [r14+28h]
0x180001d17  mov     r15, [r14]
0x180001d1a  mov     edx, [rbp+10h]; uBytes
0x180001d1d  mov     [rsp+88h+ClientLocalFlag], eax
0x180001d24  mov     rax, [r14+10h]
0x180001d28  mov     [rsp+88h+arg_18], rax
0x180001d30  mov     eax, [r14+8]
0x180001d34  mov     [rsp+88h+arg_8], eax
0x180001d3b  call    cs:__imp_LocalAlloc
0x180001d41  lea     rbx, [rbp+18h]
0x180001d45  mov     r12, rax
0x180001d48  test    rax, rax
0x180001d4b  jnz     short loc_180001D5A
0x180001d4d  mov     edi, 80070008h
0x180001d52  mov     [rbx], rax
0x180001d55  jmp     loc_180001E62
0x180001d5a  mov     ecx, [rsp+88h+ClientLocalFlag]
0x180001d61  mov     r9, rbp
0x180001d64  mov     r8, [rsp+88h+arg_18]
0x180001d6c  xor     esi, esi
0x180001d6e  mov     edx, [rsp+88h+arg_8]
0x180001d75  mov     [rbx], r12
0x180001d78  mov     rax, [r15]
0x180001d7b  mov     [rsp+88h+var_60], rdi
0x180001d80  mov     [rsp+88h+var_68], ecx
0x180001d84  mov     rcx, r15
0x180001d87  mov     rax, [rax+60h]
0x180001d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d90  mov     edi, eax
0x180001d92  test    eax, eax
0x180001d94  js      loc_180001E2C
0x180001d9a  test    byte ptr [rbp+4], 4
0x180001d9e  jz      loc_180001E9B
0x180001da4  lea     rdx, [rsp+88h+ClientLocalFlag]; ClientLocalFlag
0x180001dac  mov     [rsp+88h+ClientLocalFlag], esi
0x180001db3  xor     ecx, ecx; BindingHandle
0x180001db5  call    cs:__imp_I_RpcBindingIsClientLocal
0x180001dbb  test    eax, eax
0x180001dbd  jnz     short loc_180001DCC
0x180001dbf  cmp     [rsp+88h+ClientLocalFlag], esi
0x180001dc6  jnz     loc_180001E9B
0x180001dcc  mov     edx, 1; int
0x180001dd1  mov     rcx, r15; struct IUnknown *
0x180001dd4  call    ?FindAndReferenceServerSecureData@ADM_SECURE_DATA@@SAPEAV1@PEAUIUnknown@@H@Z; ADM_SECURE_DATA::FindAndReferenceServerSecureData(IUnknown *,int)
0x180001dd9  mov     rsi, rax
0x180001ddc  test    rax, rax
0x180001ddf  jnz     short loc_180001DEB
0x180001de1  mov     edi, 800CC806h
0x180001de6  mov     [rbx], rax
0x180001de9  jmp     short loc_180001E55
0x180001deb  mov     rcx, [rax+30h]
0x180001def  test    rcx, rcx
0x180001df2  jz      loc_180001E8D
0x180001df8  mov     rax, [rcx]
0x180001dfb  lea     rdx, [rsp+88h+pv]
0x180001e03  mov     r9d, [rbp+10h]
0x180001e07  mov     r8, [rbx]
0x180001e0a  mov     [rsp+88h+var_68], 0
0x180001e12  mov     rax, [rax]
0x180001e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e1a  mov     edi, eax
0x180001e1c  test    eax, eax
0x180001e1e  js      short loc_180001E2C
0x180001e20  mov     rax, [rsp+88h+pv]
0x180001e28  mov     [r13+0], rax
0x180001e2c  mov     qword ptr [rbx], 0
0x180001e33  test    rsi, rsi
0x180001e36  jz      short loc_180001E55
0x180001e38  or      eax, 0FFFFFFFFh
0x180001e3b  lock xadd [rsi+18h], eax
0x180001e40  cmp     eax, 1
0x180001e43  jnz     short loc_180001E55
0x180001e45  mov     rcx, rsi; this
0x180001e48  call    ??1ADM_SECURE_DATA@@QEAA@XZ; ADM_SECURE_DATA::~ADM_SECURE_DATA(void)
0x180001e4d  mov     rcx, rsi; Block
0x180001e50  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001e55  mov     rcx, r12; hMem
0x180001e58  call    cs:__imp_LocalFree
0x180001e5e  test    edi, edi
0x180001e60  jns     short loc_180001E78
0x180001e62  mov     rcx, [rsp+88h+pv]; pv
0x180001e6a  test    rcx, rcx
0x180001e6d  jz      short loc_180001E78
0x180001e6f  mov     byte ptr [rcx], 58h ; 'X'
0x180001e72  call    cs:__imp_CoTaskMemFree
0x180001e78  mov     [r14+38h], edi
0x180001e7c  add     rsp, 48h
0x180001e80  pop     r15
0x180001e82  pop     r14
0x180001e84  pop     r13
0x180001e86  pop     r12
0x180001e88  pop     rdi
0x180001e89  pop     rsi
0x180001e8a  pop     rbp
0x180001e8b  pop     rbx
0x180001e8c  retn
0x180001e8d  mov     edi, 800CC806h
0x180001e92  mov     qword ptr [rbx], 0
0x180001e99  jmp     short loc_180001E38
0x180001e9b  mov     r8d, [rbp+10h]
0x180001e9f  lea     rcx, [rsp+88h+pv]
0x180001ea7  mov     rdx, [rbx]
0x180001eaa  call    IISCryptoCreateCleartextBlob
0x180001eaf  jmp     loc_180001E1A
```
