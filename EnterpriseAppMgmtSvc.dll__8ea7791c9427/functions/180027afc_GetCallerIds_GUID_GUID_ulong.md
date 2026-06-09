# GetCallerIds(_GUID *,_GUID *,ulong *)

- ea: `0x180027afc`
- end: `0x180027cb3`
- name: `?GetCallerIds@@YAJPEAU_GUID@@0PEAK@Z`
- size: `439`
- prototype: `__int64 __fastcall(struct _GUID *, struct _GUID *, unsigned int *)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800038d0`
- `0x180003a30`
- `0x180003da0`
- `0x180004250`
- `0x180004860`
- `0x180004d00`
- `0x1800086a0`

## callees

- `0x180012b10`
- `0x180027afc`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180027b7e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180027b89`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180027b7e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180027b89`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180027b4d`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180027b4d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027c09`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027c09`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180027b63`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180027b63`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetCallerIds(struct _GUID *a1, struct _GUID *a2, unsigned int *a3)
{
  int v6; // ebx
  RPC_STATUS v7; // eax
  ExecutionManagerHelper *v8; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-20h] BYREF
  __int64 v11; // [rsp+38h] [rbp-18h] BYREF
  __int128 v12; // [rsp+40h] [rbp-10h] BYREF
  unsigned int Pid; // [rsp+70h] [rbp+20h] BYREF
  __int64 v14; // [rsp+88h] [rbp+38h] BYREF

  Pid = 0;
  v11 = 0;
  ppv = 0;
  v14 = 0;
  if ( a1 && a2 )
  {
    v6 = CoImpersonateClient();
    if ( v6 >= 0 )
    {
      v7 = I_RpcBindingInqLocalClientPID(0, &Pid);
      v6 = v7;
      if ( !v7 )
        goto LABEL_10;
      if ( v7 > 0 )
        v6 = (unsigned __int16)v7 | 0x80070000;
      if ( v6 < 0 )
      {
        CoRevertToSelf();
      }
      else
      {
LABEL_10:
        CoRevertToSelf();
        if ( a3 )
          *a3 = Pid;
        v6 = ExecutionManagerHelper::CheckAndInit(v8);
        if ( v6 >= 0 )
        {
          if ( qword_180090B90 )
          {
            v6 = ((__int64 (__fastcall *)(__int64 *))qword_180090BB0)(&v11);
            if ( v6 >= 0 )
            {
              v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct _GUID *))(*(_QWORD *)v11 + 24LL))(v11, Pid, a2);
              if ( v6 >= 0 )
              {
                v6 = CoCreateInstance(
                       &GUID_b9e511fc_e364_497a_a121_b7b3612cedce,
                       0,
                       0x17u,
                       &GUID_698d57c2_292d_4cf3_b73c_d95a6922ed9a,
                       &ppv);
                if ( v6 >= 0 )
                {
                  v12 = (__int128)*a2;
                  v6 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int64 *))(*(_QWORD *)ppv + 72LL))(
                         ppv,
                         &v12,
                         &v14);
                  if ( v6 >= 0 )
                    v6 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v14 + 224LL))(v14, a1);
                }
              }
            }
          }
          else
          {
            v6 = -2147467263;
          }
        }
      }
    }
  }
  else
  {
    v6 = -2147024809;
  }
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180027afc  mov     [rsp-18h+arg_8], rbx
0x180027b01  mov     [rsp-18h+arg_10], rsi
0x180027b06  push    rbp
0x180027b07  push    rdi
0x180027b08  push    r14
0x180027b0a  mov     rbp, rsp
0x180027b0d  sub     rsp, 50h
0x180027b11  mov     rdi, r8
0x180027b14  mov     rsi, rdx
0x180027b17  mov     r14, rcx
0x180027b1a  mov     [rbp+Pid], 0
0x180027b21  mov     [rbp+var_18], 0
0x180027b29  mov     [rbp+var_20], 0
0x180027b31  mov     [rbp+arg_18], 0
0x180027b39  test    rcx, rcx
0x180027b3c  jnz     short loc_180027B48
0x180027b3e  mov     ebx, 80070057h
0x180027b43  jmp     loc_180027C5A
0x180027b48  test    rsi, rsi
0x180027b4b  jz      short loc_180027B3E
0x180027b4d  call    cs:__imp_CoImpersonateClient
0x180027b53  mov     ebx, eax
0x180027b55  test    eax, eax
0x180027b57  js      loc_180027C5A
0x180027b5d  lea     rdx, [rbp+Pid]; Pid
0x180027b61  xor     ecx, ecx; Binding
0x180027b63  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180027b69  mov     ebx, eax
0x180027b6b  test    eax, eax
0x180027b6d  jz      short loc_180027B89
0x180027b6f  jle     short loc_180027B7A
0x180027b71  movzx   ebx, ax
0x180027b74  or      ebx, 80070000h
0x180027b7a  test    ebx, ebx
0x180027b7c  jns     short loc_180027B89
0x180027b7e  call    cs:__imp_CoRevertToSelf
0x180027b84  jmp     loc_180027C5A
0x180027b89  call    cs:__imp_CoRevertToSelf
0x180027b8f  test    rdi, rdi
0x180027b92  jz      short loc_180027B99
0x180027b94  mov     eax, [rbp+Pid]
0x180027b97  mov     [rdi], eax
0x180027b99  call    ?CheckAndInit@ExecutionManagerHelper@@AEAAJXZ; ExecutionManagerHelper::CheckAndInit(void)
0x180027b9e  mov     ebx, eax
0x180027ba0  test    eax, eax
0x180027ba2  js      loc_180027C5A
0x180027ba8  cmp     cs:qword_180090B90, 0
0x180027bb0  jz      loc_180027C55
0x180027bb6  lea     rcx, [rbp+var_18]
0x180027bba  mov     rax, cs:qword_180090BB0
0x180027bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bc6  mov     ebx, eax
0x180027bc8  test    eax, eax
0x180027bca  js      loc_180027C5A
0x180027bd0  mov     rcx, [rbp+var_18]
0x180027bd4  mov     rax, [rcx]
0x180027bd7  mov     r8, rsi
0x180027bda  mov     edx, [rbp+Pid]
0x180027bdd  mov     rax, [rax+18h]
0x180027be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027be6  mov     ebx, eax
0x180027be8  test    eax, eax
0x180027bea  js      short loc_180027C5A
0x180027bec  lea     rax, [rbp+var_20]
0x180027bf0  mov     [rsp+50h+ppv], rax; ppv
0x180027bf5  lea     r9, _GUID_698d57c2_292d_4cf3_b73c_d95a6922ed9a; riid
0x180027bfc  xor     edx, edx; pUnkOuter
0x180027bfe  lea     r8d, [rdx+17h]; dwClsContext
0x180027c02  lea     rcx, _GUID_b9e511fc_e364_497a_a121_b7b3612cedce; rclsid
0x180027c09  call    cs:__imp_CoCreateInstance
0x180027c0f  mov     ebx, eax
0x180027c11  test    eax, eax
0x180027c13  js      short loc_180027C5A
0x180027c15  mov     rcx, [rbp+var_20]
0x180027c19  movups  xmm0, xmmword ptr [rsi]
0x180027c1c  movdqu  [rbp+var_10], xmm0
0x180027c21  mov     rax, [rcx]
0x180027c24  lea     r8, [rbp+arg_18]
0x180027c28  lea     rdx, [rbp+var_10]
0x180027c2c  mov     rax, [rax+48h]
0x180027c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c35  mov     ebx, eax
0x180027c37  test    eax, eax
0x180027c39  js      short loc_180027C5A
0x180027c3b  mov     rcx, [rbp+arg_18]
0x180027c3f  mov     rax, [rcx]
0x180027c42  mov     rdx, r14
0x180027c45  mov     rax, [rax+0E0h]
0x180027c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c51  mov     ebx, eax
0x180027c53  jmp     short loc_180027C5A
0x180027c55  mov     ebx, 80004001h
0x180027c5a  mov     rcx, [rbp+arg_18]
0x180027c5e  test    rcx, rcx
0x180027c61  jz      short loc_180027C70
0x180027c63  mov     rax, [rcx]
0x180027c66  mov     rax, [rax+10h]
0x180027c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c6f  nop
0x180027c70  mov     rcx, [rbp+var_20]
0x180027c74  test    rcx, rcx
0x180027c77  jz      short loc_180027C86
0x180027c79  mov     rax, [rcx]
0x180027c7c  mov     rax, [rax+10h]
0x180027c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c85  nop
0x180027c86  mov     rcx, [rbp+var_18]
0x180027c8a  test    rcx, rcx
0x180027c8d  jz      short loc_180027C9C
0x180027c8f  mov     rax, [rcx]
0x180027c92  mov     rax, [rax+10h]
0x180027c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c9b  nop
0x180027c9c  mov     eax, ebx
0x180027c9e  lea     r11, [rsp+50h+var_s0]
0x180027ca3  mov     rbx, [r11+28h]
0x180027ca7  mov     rsi, [r11+30h]
0x180027cab  mov     rsp, r11
0x180027cae  pop     r14
0x180027cb0  pop     rdi
0x180027cb1  pop     rbp
0x180027cb2  retn
```
