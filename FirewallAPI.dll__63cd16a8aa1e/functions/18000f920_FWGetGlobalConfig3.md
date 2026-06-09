# FWGetGlobalConfig3

- ea: `0x18000f920`
- end: `0x18000fa49`
- name: `FWGetGlobalConfig3`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180025744`

## callees

- `0x180005954`
- `0x18000db60`
- `0x18000f920`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000f963`
- `ntdll!EtwEventWrite` at `0x18000f9e2`
- `ntdll!EtwEventWrite` at `0x18000f963`
- `ntdll!EtwEventWrite` at `0x18000f9e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f980`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f980`

## pseudocode

```c
__int64 __fastcall FWGetGlobalConfig3(__int64 a1, int a2, unsigned int a3, __int64 a4, int *a5, _DWORD *a6)
{
  unsigned int v10; // r9d
  __int64 v11; // rcx
  unsigned int v12; // eax
  unsigned int v13; // ebx

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetGlobalConfig, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  v10 = *(_DWORD *)(a1 + 16);
  v11 = a1;
  if ( v10 != 6 )
    v11 = 0;
  v12 = Int_FWGetOrSetGlobalConfig(1, *(_WORD *)(a1 + 2), *(_QWORD *)(a1 + 8), v10, v11, a2, a3, a4, a5, a6);
  v13 = v12;
  if ( v12 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v12);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetGlobalConfig, 0, 0);
  return v13;
}

```

## disassembly

```asm
0x18000f920  push    rbx
0x18000f922  push    rbp
0x18000f923  push    rsi
0x18000f924  push    rdi
0x18000f925  push    r12
0x18000f927  push    r14
0x18000f929  push    r15
0x18000f92b  sub     rsp, 50h
0x18000f92f  mov     r14, [rsp+88h+arg_20]
0x18000f937  mov     rbx, rcx
0x18000f93a  mov     rcx, cs:g_Provider
0x18000f941  mov     rbp, r9
0x18000f944  mov     r15, [rsp+88h+arg_28]
0x18000f94c  mov     esi, r8d
0x18000f94f  mov     edi, edx
0x18000f951  test    rcx, rcx
0x18000f954  jz      short loc_18000F969
0x18000f956  xor     r9d, r9d
0x18000f959  lea     rdx, MPS_CLNT_API_Enter_GetGlobalConfig
0x18000f960  xor     r8d, r8d
0x18000f963  call    cs:__imp_EtwEventWrite
0x18000f969  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f970  lea     r12, WPP_GLOBAL_Control
0x18000f977  cmp     rcx, r12
0x18000f97a  jnz     loc_18000FA25
0x18000f980  call    cs:__imp_GetTickCount64
0x18000f986  mov     r9d, [rbx+10h]
0x18000f98a  xor     eax, eax
0x18000f98c  mov     r8, [rbx+8]
0x18000f990  cmp     r9d, 6
0x18000f994  movzx   edx, word ptr [rbx+2]
0x18000f998  mov     rcx, rbx
0x18000f99b  mov     [rsp+88h+var_40], r15
0x18000f9a0  cmovnz  rcx, rax
0x18000f9a4  mov     [rsp+88h+var_48], r14
0x18000f9a9  mov     [rsp+88h+var_50], rbp
0x18000f9ae  mov     [rsp+88h+var_58], esi
0x18000f9b2  mov     [rsp+88h+var_60], edi
0x18000f9b6  mov     [rsp+88h+var_68], rcx
0x18000f9bb  lea     ecx, [rax+1]
0x18000f9be  call    Int_FWGetOrSetGlobalConfig
0x18000f9c3  mov     ebx, eax
0x18000f9c5  test    eax, eax
0x18000f9c7  jnz     short loc_18000F9F9
0x18000f9c9  mov     rcx, cs:g_Provider
0x18000f9d0  test    rcx, rcx
0x18000f9d3  jz      short loc_18000F9E8
0x18000f9d5  xor     r9d, r9d
0x18000f9d8  lea     rdx, MPS_CLNT_API_Exit_GetGlobalConfig
0x18000f9df  xor     r8d, r8d
0x18000f9e2  call    cs:__imp_EtwEventWrite
0x18000f9e8  mov     eax, ebx
0x18000f9ea  add     rsp, 50h
0x18000f9ee  pop     r15
0x18000f9f0  pop     r14
0x18000f9f2  pop     r12
0x18000f9f4  pop     rdi
0x18000f9f5  pop     rsi
0x18000f9f6  pop     rbp
0x18000f9f7  pop     rbx
0x18000f9f8  retn
0x18000f9f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa00  cmp     rcx, r12
0x18000fa03  jz      short loc_18000F9C9
0x18000fa05  test    byte ptr [rcx+1Ch], 1
0x18000fa09  jz      short loc_18000F9C9
0x18000fa0b  mov     rcx, [rcx+10h]
0x18000fa0f  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000fa16  mov     edx, 52h ; 'R'
0x18000fa1b  mov     r9d, ebx
0x18000fa1e  call    WPP_SF_d
0x18000fa23  jmp     short loc_18000F9C9
0x18000fa25  test    byte ptr [rcx+1Ch], 8
0x18000fa29  jz      loc_18000F980
0x18000fa2f  mov     rcx, [rcx+10h]
0x18000fa33  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000fa3a  mov     edx, 51h ; 'Q'
0x18000fa3f  call    WPP_SF_
0x18000fa44  jmp     loc_18000F980
```
