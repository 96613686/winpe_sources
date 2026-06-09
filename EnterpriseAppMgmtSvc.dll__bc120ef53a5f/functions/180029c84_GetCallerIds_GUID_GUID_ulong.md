# GetCallerIds(_GUID *,_GUID *,ulong *)

- ea: `0x180029c84`
- end: `0x180029e5a`
- name: `?GetCallerIds@@YAJPEAU_GUID@@0PEAK@Z`
- size: `470`
- prototype: `__int64 __fastcall(struct _GUID *, struct _GUID *, unsigned int *)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800039e0`
- `0x180003b40`
- `0x180003ec0`
- `0x180004380`
- `0x1800049f0`
- `0x180004eb0`
- `0x180008980`

## callees

- `0x1800134f0`
- `0x180029c84`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180029d12`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180029d23`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180029d12`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180029d23`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180029cd5`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180029cd5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029da9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029da9`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180029cf1`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180029cf1`

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
          if ( qword_180096B90 )
          {
            v6 = ((__int64 (__fastcall *)(__int64 *))qword_180096BB0)(&v11);
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
0x180029c84  mov     [rsp-18h+arg_8], rbx
0x180029c89  mov     [rsp-18h+arg_10], rsi
0x180029c8e  push    rbp
0x180029c8f  push    rdi
0x180029c90  push    r14
0x180029c92  mov     rbp, rsp
0x180029c95  sub     rsp, 50h
0x180029c99  mov     rdi, r8
0x180029c9c  mov     rsi, rdx
0x180029c9f  mov     r14, rcx
0x180029ca2  mov     [rbp+Pid], 0
0x180029ca9  mov     [rbp+var_18], 0
0x180029cb1  mov     [rbp+var_20], 0
0x180029cb9  mov     [rbp+arg_18], 0
0x180029cc1  test    rcx, rcx
0x180029cc4  jnz     short loc_180029CD0
0x180029cc6  mov     ebx, 80070057h
0x180029ccb  jmp     loc_180029E00
0x180029cd0  test    rsi, rsi
0x180029cd3  jz      short loc_180029CC6
0x180029cd5  call    cs:__imp_CoImpersonateClient
0x180029cdc  nop     dword ptr [rax+rax+00h]
0x180029ce1  mov     ebx, eax
0x180029ce3  test    eax, eax
0x180029ce5  js      loc_180029E00
0x180029ceb  lea     rdx, [rbp+Pid]; Pid
0x180029cef  xor     ecx, ecx; Binding
0x180029cf1  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180029cf8  nop     dword ptr [rax+rax+00h]
0x180029cfd  mov     ebx, eax
0x180029cff  test    eax, eax
0x180029d01  jz      short loc_180029D23
0x180029d03  jle     short loc_180029D0E
0x180029d05  movzx   ebx, ax
0x180029d08  or      ebx, 80070000h
0x180029d0e  test    ebx, ebx
0x180029d10  jns     short loc_180029D23
0x180029d12  call    cs:__imp_CoRevertToSelf
0x180029d19  nop     dword ptr [rax+rax+00h]
0x180029d1e  jmp     loc_180029E00
0x180029d23  call    cs:__imp_CoRevertToSelf
0x180029d2a  nop     dword ptr [rax+rax+00h]
0x180029d2f  test    rdi, rdi
0x180029d32  jz      short loc_180029D39
0x180029d34  mov     eax, [rbp+Pid]
0x180029d37  mov     [rdi], eax
0x180029d39  call    ?CheckAndInit@ExecutionManagerHelper@@AEAAJXZ; ExecutionManagerHelper::CheckAndInit(void)
0x180029d3e  mov     ebx, eax
0x180029d40  test    eax, eax
0x180029d42  js      loc_180029E00
0x180029d48  cmp     cs:qword_180096B90, 0
0x180029d50  jz      loc_180029DFB
0x180029d56  lea     rcx, [rbp+var_18]
0x180029d5a  mov     rax, cs:qword_180096BB0
0x180029d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d66  mov     ebx, eax
0x180029d68  test    eax, eax
0x180029d6a  js      loc_180029E00
0x180029d70  mov     rcx, [rbp+var_18]
0x180029d74  mov     rax, [rcx]
0x180029d77  mov     r8, rsi
0x180029d7a  mov     edx, [rbp+Pid]
0x180029d7d  mov     rax, [rax+18h]
0x180029d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d86  mov     ebx, eax
0x180029d88  test    eax, eax
0x180029d8a  js      short loc_180029E00
0x180029d8c  lea     rax, [rbp+var_20]
0x180029d90  mov     [rsp+50h+ppv], rax; ppv
0x180029d95  lea     r9, _GUID_698d57c2_292d_4cf3_b73c_d95a6922ed9a; riid
0x180029d9c  xor     edx, edx; pUnkOuter
0x180029d9e  lea     r8d, [rdx+17h]; dwClsContext
0x180029da2  lea     rcx, _GUID_b9e511fc_e364_497a_a121_b7b3612cedce; rclsid
0x180029da9  call    cs:__imp_CoCreateInstance
0x180029db0  nop     dword ptr [rax+rax+00h]
0x180029db5  mov     ebx, eax
0x180029db7  test    eax, eax
0x180029db9  js      short loc_180029E00
0x180029dbb  mov     rcx, [rbp+var_20]
0x180029dbf  movups  xmm0, xmmword ptr [rsi]
0x180029dc2  movdqu  [rbp+var_10], xmm0
0x180029dc7  mov     rax, [rcx]
0x180029dca  lea     r8, [rbp+arg_18]
0x180029dce  lea     rdx, [rbp+var_10]
0x180029dd2  mov     rax, [rax+48h]
0x180029dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ddb  mov     ebx, eax
0x180029ddd  test    eax, eax
0x180029ddf  js      short loc_180029E00
0x180029de1  mov     rcx, [rbp+arg_18]
0x180029de5  mov     rax, [rcx]
0x180029de8  mov     rdx, r14
0x180029deb  mov     rax, [rax+0E0h]
0x180029df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029df7  mov     ebx, eax
0x180029df9  jmp     short loc_180029E00
0x180029dfb  mov     ebx, 80004001h
0x180029e00  mov     rcx, [rbp+arg_18]
0x180029e04  test    rcx, rcx
0x180029e07  jz      short loc_180029E16
0x180029e09  mov     rax, [rcx]
0x180029e0c  mov     rax, [rax+10h]
0x180029e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e15  nop
0x180029e16  mov     rcx, [rbp+var_20]
0x180029e1a  test    rcx, rcx
0x180029e1d  jz      short loc_180029E2C
0x180029e1f  mov     rax, [rcx]
0x180029e22  mov     rax, [rax+10h]
0x180029e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e2b  nop
0x180029e2c  mov     rcx, [rbp+var_18]
0x180029e30  test    rcx, rcx
0x180029e33  jz      short loc_180029E42
0x180029e35  mov     rax, [rcx]
0x180029e38  mov     rax, [rax+10h]
0x180029e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e41  nop
0x180029e42  mov     eax, ebx
0x180029e44  lea     r11, [rsp+50h+var_s0]
0x180029e49  mov     rbx, [r11+28h]
0x180029e4d  mov     rsi, [r11+30h]
0x180029e51  mov     rsp, r11
0x180029e54  pop     r14
0x180029e56  pop     rdi
0x180029e57  pop     rbp
0x180029e58  retn
```
