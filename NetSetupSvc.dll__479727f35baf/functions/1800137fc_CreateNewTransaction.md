# CreateNewTransaction

- ea: `0x1800137fc`
- end: `0x180013934`
- name: `CreateNewTransaction`
- size: `312`
- prototype: `void __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x180013230`

## callees

- `0x1800027c0`
- `0x18000d4ac`
- `0x18000d8ec`
- `0x18000fd7c`
- `0x1800137fc`
- `0x180031010`

## pseudocode

```c
void __fastcall CreateNewTransaction(_QWORD *a1, __int64 a2)
{
  __int128 v4; // xmm1
  __int64 *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  volatile signed __int32 *v8; // rbx
  std::_Ref_count_base *v9; // rbx
  __int64 v10; // [rsp+20h] [rbp-39h] BYREF
  std::_Ref_count_base *v11; // [rsp+28h] [rbp-31h]
  __int128 v12; // [rsp+30h] [rbp-29h] BYREF
  __int64 v13; // [rsp+40h] [rbp-19h]
  _OWORD v14[5]; // [rsp+50h] [rbp-9h] BYREF

  v12 = 0;
  LODWORD(v12) = 3;
  v13 = 0;
  NetSetupService::WaitForDevicesReady(g_NetSetupService);
  v14[0] = *((_OWORD *)g_NetSetupService + 19);
  v14[1] = *((_OWORD *)g_NetSetupService + 20);
  v14[2] = *((_OWORD *)g_NetSetupService + 21);
  v4 = *((_OWORD *)g_NetSetupService + 22);
  *((_QWORD *)&v12 + 1) = v14;
  v14[3] = v4;
  v14[4] = *(_OWORD *)a1;
  v5 = NetSetupSvcTransactionCoordinator::CreateNewTransaction(
         (NetSetupService *)((char *)g_NetSetupService + 32),
         &v10,
         a1,
         (__int64)&v12);
  v6 = *v5;
  v7 = v5[1];
  *v5 = 0;
  v5[1] = 0;
  *(_QWORD *)(a2 + 8) = v6;
  v8 = *(volatile signed __int32 **)(a2 + 16);
  *(_QWORD *)(a2 + 16) = v7;
  if ( v8 && !_InterlockedDecrement(v8 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
    std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v8);
  }
  v9 = v11;
  if ( v11 )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)v11 + 2) )
    {
      (**(void (__fastcall ***)(std::_Ref_count_base *))v9)(v9);
      std::_Ref_count_base::_Decwref(v9);
    }
  }
}

```

## disassembly

```asm
0x1800137fc  mov     [rsp-8+arg_10], rbx
0x180013801  mov     [rsp-8+arg_18], rdi
0x180013806  push    rbp
0x180013807  lea     rbp, [rsp-57h]
0x18001380c  sub     rsp, 0B0h
0x180013813  mov     rax, cs:__security_cookie
0x18001381a  xor     rax, rsp
0x18001381d  mov     [rbp+57h+var_10], rax
0x180013821  xorps   xmm0, xmm0
0x180013824  mov     rbx, rcx
0x180013827  mov     rcx, cs:?g_NetSetupService@@3PEAVNetSetupService@@EA; this
0x18001382e  xor     eax, eax
0x180013830  movups  [rbp+57h+var_80], xmm0
0x180013834  mov     dword ptr [rbp+57h+var_80], 3
0x18001383b  mov     rdi, rdx
0x18001383e  mov     [rbp+57h+var_70], rax
0x180013842  call    ?WaitForDevicesReady@NetSetupService@@QEAAXXZ; NetSetupService::WaitForDevicesReady(void)
0x180013847  mov     rcx, cs:?g_NetSetupService@@3PEAVNetSetupService@@EA; NetSetupService * g_NetSetupService
0x18001384e  lea     rax, [rbp+57h+var_60]
0x180013852  lea     r9, [rbp+57h+var_80]
0x180013856  mov     r8, rbx
0x180013859  lea     rdx, [rbp+57h+var_90]
0x18001385d  movups  xmm0, xmmword ptr [rcx+130h]
0x180013864  movaps  [rbp+57h+var_60], xmm0
0x180013868  movups  xmm1, xmmword ptr [rcx+140h]
0x18001386f  movaps  [rbp+57h+var_50], xmm1
0x180013873  movups  xmm0, xmmword ptr [rcx+150h]
0x18001387a  movaps  [rbp+57h+var_40], xmm0
0x18001387e  movups  xmm1, xmmword ptr [rcx+160h]
0x180013885  add     rcx, 20h ; ' '; struct StackLock *
0x180013889  mov     qword ptr [rbp+57h+var_80+8], rax
0x18001388d  movaps  [rbp+57h+var_30], xmm1
0x180013891  movaps  xmm1, xmmword ptr [rbx]
0x180013894  movdqu  [rbp+57h+var_20], xmm1
0x180013899  call    ?CreateNewTransaction@NetSetupSvcTransactionCoordinator@@QEAA?AV?$shared_ptr@UNetSetupSvcTxHolder@@@std@@AEBU_GUID@@PEAU_NETSETUP_ENVIRONMENT@@@Z; NetSetupSvcTransactionCoordinator::CreateNewTransaction(_GUID const &,_NETSETUP_ENVIRONMENT *)
0x18001389e  mov     rcx, [rax]
0x1800138a1  mov     rdx, [rax+8]
0x1800138a5  mov     qword ptr [rax], 0
0x1800138ac  mov     qword ptr [rax+8], 0
0x1800138b4  mov     [rdi+8], rcx
0x1800138b8  mov     rbx, [rdi+10h]
0x1800138bc  mov     [rdi+10h], rdx
0x1800138c0  or      edi, 0FFFFFFFFh
0x1800138c3  test    rbx, rbx
0x1800138c6  jz      short loc_1800138E9
0x1800138c8  mov     eax, edi
0x1800138ca  lock xadd [rbx+8], eax
0x1800138cf  add     eax, edi
0x1800138d1  jnz     short loc_1800138E9
0x1800138d3  mov     rax, [rbx]
0x1800138d6  mov     rcx, rbx
0x1800138d9  mov     rax, [rax]
0x1800138dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138e1  mov     rcx, rbx; this
0x1800138e4  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800138e9  mov     rbx, [rbp+57h+var_88]
0x1800138ed  test    rbx, rbx
0x1800138f0  jz      short loc_180013913
0x1800138f2  mov     eax, edi
0x1800138f4  lock xadd [rbx+8], eax
0x1800138f9  add     eax, edi
0x1800138fb  jnz     short loc_180013913
0x1800138fd  mov     rax, [rbx]
0x180013900  mov     rcx, rbx
0x180013903  mov     rax, [rax]
0x180013906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001390b  mov     rcx, rbx; this
0x18001390e  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180013913  mov     rcx, [rbp+57h+var_10]
0x180013917  xor     rcx, rsp; StackCookie
0x18001391a  call    __security_check_cookie
0x18001391f  lea     r11, [rsp+0B0h+var_s0]
0x180013927  mov     rbx, [r11+20h]
0x18001392b  mov     rdi, [r11+28h]
0x18001392f  mov     rsp, r11
0x180013932  pop     rbp
0x180013933  retn
```
