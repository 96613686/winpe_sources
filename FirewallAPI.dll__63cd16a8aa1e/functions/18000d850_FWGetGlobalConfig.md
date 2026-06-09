# FWGetGlobalConfig

- ea: `0x18000d850`
- end: `0x18000d9c5`
- name: `FWGetGlobalConfig`
- size: `373`
- prototype: ``
- caller_count: `12`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180005da0`
- `0x18000b390`
- `0x18000bcd0`
- `0x18000c560`
- `0x18000db60`
- `0x18000edf0`
- `0x18000f000`
- `0x180018ef0`
- `0x180020370`
- `0x18002e484`
- `0x180031080`
- `0x180033ff8`

## callees

- `0x180005954`
- `0x18000d850`
- `0x18000db60`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000d894`
- `ntdll!EtwEventWrite` at `0x18000d922`
- `ntdll!EtwEventWrite` at `0x18000d894`
- `ntdll!EtwEventWrite` at `0x18000d922`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000d8b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000d8b7`

## pseudocode

```c
__int64 __fastcall FWGetGlobalConfig(
        unsigned __int16 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        int *a7)
{
  unsigned int v11; // eax
  unsigned int v12; // ebx
  FwPolicy2 *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  unsigned __int64 v17; // rax

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetGlobalConfig, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  if ( a3 == 6 )
    goto LABEL_8;
  if ( !a2 )
    goto LABEL_8;
  v17 = -1;
  do
    ++v17;
  while ( *(_WORD *)(a2 + 2 * v17) );
  if ( v17 <= 0xFF )
  {
LABEL_8:
    v11 = Int_FWGetOrSetGlobalConfig(1, a1, a2, a3, 0, a4, a5, a6, a7, 0);
    v12 = v11;
    if ( v11 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 80;
        v16 = v11;
LABEL_15:
        WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v16);
      }
    }
  }
  else
  {
    v12 = 87;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 79;
      v16 = 87;
      goto LABEL_15;
    }
  }
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetGlobalConfig, 0, 0);
  return v12;
}

```

## disassembly

```asm
0x18000d850  push    rbx
0x18000d852  push    rbp
0x18000d853  push    rsi
0x18000d854  push    rdi
0x18000d855  push    r12
0x18000d857  push    r14
0x18000d859  push    r15
0x18000d85b  sub     rsp, 50h
0x18000d85f  mov     r14, [rsp+88h+arg_28]
0x18000d867  movzx   esi, cx
0x18000d86a  mov     rcx, cs:g_Provider
0x18000d871  mov     ebp, r9d
0x18000d874  mov     r15, [rsp+88h+arg_30]
0x18000d87c  mov     ebx, r8d
0x18000d87f  mov     rdi, rdx
0x18000d882  test    rcx, rcx
0x18000d885  jz      short loc_18000D89A
0x18000d887  xor     r9d, r9d
0x18000d88a  lea     rdx, MPS_CLNT_API_Enter_GetGlobalConfig
0x18000d891  xor     r8d, r8d
0x18000d894  call    cs:__imp_EtwEventWrite
0x18000d89a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8a1  lea     r12, WPP_GLOBAL_Control
0x18000d8a8  cmp     rcx, r12
0x18000d8ab  jz      short loc_18000D8B7
0x18000d8ad  test    byte ptr [rcx+1Ch], 8
0x18000d8b1  jnz     loc_18000D965
0x18000d8b7  call    cs:__imp_GetTickCount64
0x18000d8bd  cmp     ebx, 6
0x18000d8c0  jz      short loc_18000D8CB
0x18000d8c2  test    rdi, rdi
0x18000d8c5  jnz     loc_18000D97F
0x18000d8cb  mov     eax, [rsp+88h+arg_20]
0x18000d8d2  xor     ecx, ecx
0x18000d8d4  mov     [rsp+88h+var_40], rcx
0x18000d8d9  mov     r9d, ebx
0x18000d8dc  mov     [rsp+88h+var_48], r15
0x18000d8e1  mov     r8, rdi
0x18000d8e4  mov     [rsp+88h+var_50], r14
0x18000d8e9  movzx   edx, si
0x18000d8ec  mov     [rsp+88h+var_58], eax
0x18000d8f0  mov     [rsp+88h+var_60], ebp
0x18000d8f4  mov     [rsp+88h+var_68], rcx
0x18000d8f9  mov     ecx, 1
0x18000d8fe  call    Int_FWGetOrSetGlobalConfig
0x18000d903  mov     ebx, eax
0x18000d905  test    eax, eax
0x18000d907  jnz     short loc_18000D939
0x18000d909  mov     rcx, cs:g_Provider
0x18000d910  test    rcx, rcx
0x18000d913  jz      short loc_18000D928
0x18000d915  xor     r9d, r9d
0x18000d918  lea     rdx, MPS_CLNT_API_Exit_GetGlobalConfig
0x18000d91f  xor     r8d, r8d
0x18000d922  call    cs:__imp_EtwEventWrite
0x18000d928  mov     eax, ebx
0x18000d92a  add     rsp, 50h
0x18000d92e  pop     r15
0x18000d930  pop     r14
0x18000d932  pop     r12
0x18000d934  pop     rdi
0x18000d935  pop     rsi
0x18000d936  pop     rbp
0x18000d937  pop     rbx
0x18000d938  retn
0x18000d939  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d940  cmp     rcx, r12
0x18000d943  jz      short loc_18000D909
0x18000d945  test    byte ptr [rcx+1Ch], 1
0x18000d949  jz      short loc_18000D909
0x18000d94b  mov     edx, 50h ; 'P'
0x18000d950  mov     r9d, eax
0x18000d953  mov     rcx, [rcx+10h]
0x18000d957  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000d95e  call    WPP_SF_d
0x18000d963  jmp     short loc_18000D909
0x18000d965  mov     rcx, [rcx+10h]
0x18000d969  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000d970  mov     edx, 4Eh ; 'N'
0x18000d975  call    WPP_SF_
0x18000d97a  jmp     loc_18000D8B7
0x18000d97f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000d986  inc     rax
0x18000d989  cmp     word ptr [rdi+rax*2], 0
0x18000d98e  jnz     short loc_18000D986
0x18000d990  cmp     rax, 0FFh
0x18000d996  jbe     loc_18000D8CB
0x18000d99c  mov     ebx, 57h ; 'W'
0x18000d9a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9a8  cmp     rcx, r12
0x18000d9ab  jz      loc_18000D909
0x18000d9b1  test    byte ptr [rcx+1Ch], 1
0x18000d9b5  jz      loc_18000D909
0x18000d9bb  mov     edx, 4Fh ; 'O'
0x18000d9c0  mov     r9d, ebx
0x18000d9c3  jmp     short loc_18000D953
```
