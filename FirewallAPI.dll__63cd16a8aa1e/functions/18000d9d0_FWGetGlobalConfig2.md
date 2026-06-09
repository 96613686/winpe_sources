# FWGetGlobalConfig2

- ea: `0x18000d9d0`
- end: `0x18000db53`
- name: `FWGetGlobalConfig2`
- size: `387`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180005954`
- `0x18000d9d0`
- `0x18000db60`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000da1e`
- `ntdll!EtwEventWrite` at `0x18000daae`
- `ntdll!EtwEventWrite` at `0x18000da1e`
- `ntdll!EtwEventWrite` at `0x18000daae`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000da41`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000da41`

## pseudocode

```c
__int64 __fastcall FWGetGlobalConfig2(
        unsigned __int16 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        int *a7,
        _DWORD *a8)
{
  unsigned int v12; // eax
  unsigned int v13; // ebx
  FwPolicy2 *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned __int64 v18; // rax

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetGlobalConfig, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  if ( a3 == 6 )
    goto LABEL_8;
  if ( !a2 )
    goto LABEL_8;
  v18 = -1;
  do
    ++v18;
  while ( *(_WORD *)(a2 + 2 * v18) );
  if ( v18 <= 0xFF )
  {
LABEL_8:
    v12 = Int_FWGetOrSetGlobalConfig(1, a1, a2, a3, 0, a4, a5, a6, a7, a8);
    v13 = v12;
    if ( v12 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = 80;
        v17 = v12;
LABEL_15:
        WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v17);
      }
    }
  }
  else
  {
    v13 = 87;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = 79;
      v17 = 87;
      goto LABEL_15;
    }
  }
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetGlobalConfig, 0, 0);
  return v13;
}

```

## disassembly

```asm
0x18000d9d0  push    rbx
0x18000d9d2  push    rbp
0x18000d9d3  push    rsi
0x18000d9d4  push    rdi
0x18000d9d5  push    r12
0x18000d9d7  push    r13
0x18000d9d9  push    r14
0x18000d9db  push    r15
0x18000d9dd  sub     rsp, 58h
0x18000d9e1  mov     r14, [rsp+98h+arg_28]
0x18000d9e9  movzx   esi, cx
0x18000d9ec  mov     rcx, cs:g_Provider
0x18000d9f3  mov     ebp, r9d
0x18000d9f6  mov     r15, [rsp+98h+arg_30]
0x18000d9fe  mov     ebx, r8d
0x18000da01  mov     r12, [rsp+98h+arg_38]
0x18000da09  mov     rdi, rdx
0x18000da0c  test    rcx, rcx
0x18000da0f  jz      short loc_18000DA24
0x18000da11  xor     r9d, r9d
0x18000da14  lea     rdx, MPS_CLNT_API_Enter_GetGlobalConfig
0x18000da1b  xor     r8d, r8d
0x18000da1e  call    cs:__imp_EtwEventWrite
0x18000da24  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da2b  lea     r13, WPP_GLOBAL_Control
0x18000da32  cmp     rcx, r13
0x18000da35  jz      short loc_18000DA41
0x18000da37  test    byte ptr [rcx+1Ch], 8
0x18000da3b  jnz     loc_18000DAF3
0x18000da41  call    cs:__imp_GetTickCount64
0x18000da47  cmp     ebx, 6
0x18000da4a  jz      short loc_18000DA55
0x18000da4c  test    rdi, rdi
0x18000da4f  jnz     loc_18000DB0D
0x18000da55  mov     eax, [rsp+98h+arg_20]
0x18000da5c  mov     r9d, ebx
0x18000da5f  mov     [rsp+98h+var_50], r12
0x18000da64  mov     r8, rdi
0x18000da67  mov     [rsp+98h+var_58], r15
0x18000da6c  movzx   edx, si
0x18000da6f  mov     [rsp+98h+var_60], r14
0x18000da74  mov     ecx, 1
0x18000da79  mov     [rsp+98h+var_68], eax
0x18000da7d  mov     [rsp+98h+var_70], ebp
0x18000da81  mov     [rsp+98h+var_78], 0
0x18000da8a  call    Int_FWGetOrSetGlobalConfig
0x18000da8f  mov     ebx, eax
0x18000da91  test    eax, eax
0x18000da93  jnz     short loc_18000DAC7
0x18000da95  mov     rcx, cs:g_Provider
0x18000da9c  test    rcx, rcx
0x18000da9f  jz      short loc_18000DAB4
0x18000daa1  xor     r9d, r9d
0x18000daa4  lea     rdx, MPS_CLNT_API_Exit_GetGlobalConfig
0x18000daab  xor     r8d, r8d
0x18000daae  call    cs:__imp_EtwEventWrite
0x18000dab4  mov     eax, ebx
0x18000dab6  add     rsp, 58h
0x18000daba  pop     r15
0x18000dabc  pop     r14
0x18000dabe  pop     r13
0x18000dac0  pop     r12
0x18000dac2  pop     rdi
0x18000dac3  pop     rsi
0x18000dac4  pop     rbp
0x18000dac5  pop     rbx
0x18000dac6  retn
0x18000dac7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dace  cmp     rcx, r13
0x18000dad1  jz      short loc_18000DA95
0x18000dad3  test    byte ptr [rcx+1Ch], 1
0x18000dad7  jz      short loc_18000DA95
0x18000dad9  mov     edx, 50h ; 'P'
0x18000dade  mov     r9d, eax
0x18000dae1  mov     rcx, [rcx+10h]
0x18000dae5  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000daec  call    WPP_SF_d
0x18000daf1  jmp     short loc_18000DA95
0x18000daf3  mov     rcx, [rcx+10h]
0x18000daf7  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000dafe  mov     edx, 4Eh ; 'N'
0x18000db03  call    WPP_SF_
0x18000db08  jmp     loc_18000DA41
0x18000db0d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000db14  inc     rax
0x18000db17  cmp     word ptr [rdi+rax*2], 0
0x18000db1c  jnz     short loc_18000DB14
0x18000db1e  cmp     rax, 0FFh
0x18000db24  jbe     loc_18000DA55
0x18000db2a  mov     ebx, 57h ; 'W'
0x18000db2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db36  cmp     rcx, r13
0x18000db39  jz      loc_18000DA95
0x18000db3f  test    byte ptr [rcx+1Ch], 1
0x18000db43  jz      loc_18000DA95
0x18000db49  mov     edx, 4Fh ; 'O'
0x18000db4e  mov     r9d, ebx
0x18000db51  jmp     short loc_18000DAE1
```
