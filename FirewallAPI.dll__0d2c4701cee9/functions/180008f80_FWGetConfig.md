# FWGetConfig

- ea: `0x180008f80`
- end: `0x1800090ca`
- name: `FWGetConfig`
- size: `330`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x180005e0c`
- `0x180008f80`
- `0x180009210`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180008fda`
- `ntdll!EtwEventWrite` at `0x180009059`
- `ntdll!EtwEventWrite` at `0x180008fda`
- `ntdll!EtwEventWrite` at `0x180009059`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009003`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009003`

## pseudocode

```c
__int64 __fastcall FWGetConfig(__int64 a1, unsigned int a2, unsigned int a3, int a4, __int64 a5, int *a6)
{
  unsigned int v10; // eax
  unsigned int v11; // ebx

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  v10 = Int_FWGetOrSetConfig(1u, a1, a2, a3, a4, a5, a6);
  v11 = v10;
  if ( v10 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v10);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
  return v11;
}

```

## disassembly

```asm
0x180008f80  push    rbx
0x180008f82  push    rbp
0x180008f83  push    rsi
0x180008f84  push    rdi
0x180008f85  push    r12
0x180008f87  push    r14
0x180008f89  push    r15
0x180008f8b  sub     rsp, 50h
0x180008f8f  mov     rax, cs:__security_cookie
0x180008f96  xor     rax, rsp
0x180008f99  mov     [rsp+88h+var_40], rax
0x180008f9e  mov     r14, [rsp+88h+arg_20]
0x180008fa6  mov     rbx, rcx
0x180008fa9  mov     rcx, cs:g_Provider
0x180008fb0  mov     ebp, r9d
0x180008fb3  mov     r15, [rsp+88h+arg_28]
0x180008fbb  mov     esi, r8d
0x180008fbe  mov     [rsp+88h+var_48], 0
0x180008fc6  mov     edi, edx
0x180008fc8  test    rcx, rcx
0x180008fcb  jz      short loc_180008FE6
0x180008fcd  xor     r9d, r9d
0x180008fd0  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x180008fd7  xor     r8d, r8d
0x180008fda  call    cs:__imp_EtwEventWrite
0x180008fe1  nop     dword ptr [rax+rax+00h]
0x180008fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fed  lea     r12, WPP_GLOBAL_Control
0x180008ff4  cmp     rcx, r12
0x180008ff7  jz      short loc_180009003
0x180008ff9  test    byte ptr [rcx+1Ch], 8
0x180008ffd  jnz     loc_1800090B0
0x180009003  call    cs:__imp_GetTickCount64
0x18000900a  nop     dword ptr [rax+rax+00h]
0x18000900f  lea     rax, [rsp+88h+var_48]
0x180009014  mov     r9d, esi
0x180009017  mov     [rsp+88h+var_50], rax
0x18000901c  mov     r8d, edi
0x18000901f  mov     [rsp+88h+var_58], r15
0x180009024  mov     rdx, rbx
0x180009027  mov     [rsp+88h+var_60], r14
0x18000902c  mov     ecx, 1
0x180009031  mov     [rsp+88h+var_68], ebp
0x180009035  call    Int_FWGetOrSetConfig
0x18000903a  mov     ebx, eax
0x18000903c  test    eax, eax
0x18000903e  jnz     short loc_180009084
0x180009040  mov     rcx, cs:g_Provider
0x180009047  test    rcx, rcx
0x18000904a  jz      short loc_180009065
0x18000904c  xor     r9d, r9d
0x18000904f  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x180009056  xor     r8d, r8d
0x180009059  call    cs:__imp_EtwEventWrite
0x180009060  nop     dword ptr [rax+rax+00h]
0x180009065  mov     eax, ebx
0x180009067  mov     rcx, [rsp+88h+var_40]
0x18000906c  xor     rcx, rsp; StackCookie
0x18000906f  call    __security_check_cookie
0x180009074  add     rsp, 50h
0x180009078  pop     r15
0x18000907a  pop     r14
0x18000907c  pop     r12
0x18000907e  pop     rdi
0x18000907f  pop     rsi
0x180009080  pop     rbp
0x180009081  pop     rbx
0x180009082  retn
0x180009084  mov     rcx, cs:WPP_GLOBAL_Control
0x18000908b  cmp     rcx, r12
0x18000908e  jz      short loc_180009040
0x180009090  test    byte ptr [rcx+1Ch], 1
0x180009094  jz      short loc_180009040
0x180009096  mov     rcx, [rcx+10h]
0x18000909a  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800090a1  mov     edx, 6Ah ; 'j'
0x1800090a6  mov     r9d, ebx
0x1800090a9  call    WPP_SF_d
0x1800090ae  jmp     short loc_180009040
0x1800090b0  mov     rcx, [rcx+10h]
0x1800090b4  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800090bb  mov     edx, 69h ; 'i'
0x1800090c0  call    WPP_SF_
0x1800090c5  jmp     loc_180009003
```
