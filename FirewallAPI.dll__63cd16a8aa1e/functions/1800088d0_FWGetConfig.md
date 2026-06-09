# FWGetConfig

- ea: `0x1800088d0`
- end: `0x180008a07`
- name: `FWGetConfig`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x180005954`
- `0x1800088d0`
- `0x180008b30`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000892a`
- `ntdll!EtwEventWrite` at `0x18000899d`
- `ntdll!EtwEventWrite` at `0x18000892a`
- `ntdll!EtwEventWrite` at `0x18000899d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000894d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000894d`

## pseudocode

```c
__int64 __fastcall FWGetConfig(__int64 a1, unsigned int a2, unsigned int a3, int a4, __int64 a5, int *a6)
{
  unsigned int v10; // eax
  unsigned int v11; // ebx

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  v10 = Int_FWGetOrSetConfig(1u, a1, a2, a3, a4, a5, a6);
  v11 = v10;
  if ( v10 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v10);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
  return v11;
}

```

## disassembly

```asm
0x1800088d0  push    rbx
0x1800088d2  push    rbp
0x1800088d3  push    rsi
0x1800088d4  push    rdi
0x1800088d5  push    r12
0x1800088d7  push    r14
0x1800088d9  push    r15
0x1800088db  sub     rsp, 50h
0x1800088df  mov     rax, cs:__security_cookie
0x1800088e6  xor     rax, rsp
0x1800088e9  mov     [rsp+88h+var_40], rax
0x1800088ee  mov     r14, [rsp+88h+arg_20]
0x1800088f6  mov     rbx, rcx
0x1800088f9  mov     rcx, cs:g_Provider
0x180008900  mov     ebp, r9d
0x180008903  mov     r15, [rsp+88h+arg_28]
0x18000890b  mov     esi, r8d
0x18000890e  mov     [rsp+88h+var_48], 0
0x180008916  mov     edi, edx
0x180008918  test    rcx, rcx
0x18000891b  jz      short loc_180008930
0x18000891d  xor     r9d, r9d
0x180008920  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x180008927  xor     r8d, r8d
0x18000892a  call    cs:__imp_EtwEventWrite
0x180008930  mov     rcx, cs:WPP_GLOBAL_Control
0x180008937  lea     r12, WPP_GLOBAL_Control
0x18000893e  cmp     rcx, r12
0x180008941  jz      short loc_18000894D
0x180008943  test    byte ptr [rcx+1Ch], 8
0x180008947  jnz     loc_1800089ED
0x18000894d  call    cs:__imp_GetTickCount64
0x180008953  lea     rax, [rsp+88h+var_48]
0x180008958  mov     r9d, esi
0x18000895b  mov     [rsp+88h+var_50], rax
0x180008960  mov     r8d, edi
0x180008963  mov     [rsp+88h+var_58], r15
0x180008968  mov     rdx, rbx
0x18000896b  mov     [rsp+88h+var_60], r14
0x180008970  mov     ecx, 1
0x180008975  mov     [rsp+88h+var_68], ebp
0x180008979  call    Int_FWGetOrSetConfig
0x18000897e  mov     ebx, eax
0x180008980  test    eax, eax
0x180008982  jnz     short loc_1800089C1
0x180008984  mov     rcx, cs:g_Provider
0x18000898b  test    rcx, rcx
0x18000898e  jz      short loc_1800089A3
0x180008990  xor     r9d, r9d
0x180008993  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x18000899a  xor     r8d, r8d
0x18000899d  call    cs:__imp_EtwEventWrite
0x1800089a3  mov     eax, ebx
0x1800089a5  mov     rcx, [rsp+88h+var_40]
0x1800089aa  xor     rcx, rsp; StackCookie
0x1800089ad  call    __security_check_cookie
0x1800089b2  add     rsp, 50h
0x1800089b6  pop     r15
0x1800089b8  pop     r14
0x1800089ba  pop     r12
0x1800089bc  pop     rdi
0x1800089bd  pop     rsi
0x1800089be  pop     rbp
0x1800089bf  pop     rbx
0x1800089c0  retn
0x1800089c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800089c8  cmp     rcx, r12
0x1800089cb  jz      short loc_180008984
0x1800089cd  test    byte ptr [rcx+1Ch], 1
0x1800089d1  jz      short loc_180008984
0x1800089d3  mov     rcx, [rcx+10h]
0x1800089d7  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800089de  mov     edx, 6Bh ; 'k'
0x1800089e3  mov     r9d, ebx
0x1800089e6  call    WPP_SF_d
0x1800089eb  jmp     short loc_180008984
0x1800089ed  mov     rcx, [rcx+10h]
0x1800089f1  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800089f8  mov     edx, 6Ah ; 'j'
0x1800089fd  call    WPP_SF_
0x180008a02  jmp     loc_18000894D
```
