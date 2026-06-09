# FWGetConfig2

- ea: `0x180008a10`
- end: `0x180008b2a`
- name: `FWGetConfig2`
- size: `282`
- prototype: ``
- caller_count: `10`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b390`
- `0x180018ef0`
- `0x180020370`
- `0x180025744`
- `0x18002e484`
- `0x1800312cc`
- `0x180031770`
- `0x180031d30`
- `0x180032de0`
- `0x1800376e0`

## callees

- `0x180005954`
- `0x180008a10`
- `0x180008b30`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180008a5d`
- `ntdll!EtwEventWrite` at `0x180008acb`
- `ntdll!EtwEventWrite` at `0x180008a5d`
- `ntdll!EtwEventWrite` at `0x180008acb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008a80`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008a80`

## pseudocode

```c
__int64 __fastcall FWGetConfig2(__int64 a1, unsigned int a2, unsigned int a3, int a4, __int64 a5, int *a6)
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
0x180008a10  push    rbx
0x180008a12  push    rbp
0x180008a13  push    rsi
0x180008a14  push    rdi
0x180008a15  push    r12
0x180008a17  push    r13
0x180008a19  push    r14
0x180008a1b  push    r15
0x180008a1d  sub     rsp, 48h
0x180008a21  mov     r14, [rsp+88h+arg_20]
0x180008a29  mov     rbx, rcx
0x180008a2c  mov     rcx, cs:g_Provider
0x180008a33  mov     ebp, r9d
0x180008a36  mov     r15, [rsp+88h+arg_28]
0x180008a3e  mov     esi, r8d
0x180008a41  mov     r12, [rsp+88h+arg_30]
0x180008a49  mov     edi, edx
0x180008a4b  test    rcx, rcx
0x180008a4e  jz      short loc_180008A63
0x180008a50  xor     r9d, r9d
0x180008a53  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x180008a5a  xor     r8d, r8d
0x180008a5d  call    cs:__imp_EtwEventWrite
0x180008a63  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a6a  lea     r13, WPP_GLOBAL_Control
0x180008a71  cmp     rcx, r13
0x180008a74  jz      short loc_180008A80
0x180008a76  test    byte ptr [rcx+1Ch], 8
0x180008a7a  jnz     loc_180008B10
0x180008a80  call    cs:__imp_GetTickCount64
0x180008a86  mov     [rsp+88h+var_50], r12
0x180008a8b  mov     r9d, esi
0x180008a8e  mov     [rsp+88h+var_58], r15
0x180008a93  mov     r8d, edi
0x180008a96  mov     [rsp+88h+var_60], r14
0x180008a9b  mov     rdx, rbx
0x180008a9e  mov     ecx, 1
0x180008aa3  mov     [rsp+88h+var_68], ebp
0x180008aa7  call    Int_FWGetOrSetConfig
0x180008aac  mov     ebx, eax
0x180008aae  test    eax, eax
0x180008ab0  jnz     short loc_180008AE4
0x180008ab2  mov     rcx, cs:g_Provider
0x180008ab9  test    rcx, rcx
0x180008abc  jz      short loc_180008AD1
0x180008abe  xor     r9d, r9d
0x180008ac1  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x180008ac8  xor     r8d, r8d
0x180008acb  call    cs:__imp_EtwEventWrite
0x180008ad1  mov     eax, ebx
0x180008ad3  add     rsp, 48h
0x180008ad7  pop     r15
0x180008ad9  pop     r14
0x180008adb  pop     r13
0x180008add  pop     r12
0x180008adf  pop     rdi
0x180008ae0  pop     rsi
0x180008ae1  pop     rbp
0x180008ae2  pop     rbx
0x180008ae3  retn
0x180008ae4  mov     rcx, cs:WPP_GLOBAL_Control
0x180008aeb  cmp     rcx, r13
0x180008aee  jz      short loc_180008AB2
0x180008af0  test    byte ptr [rcx+1Ch], 1
0x180008af4  jz      short loc_180008AB2
0x180008af6  mov     rcx, [rcx+10h]
0x180008afa  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180008b01  mov     edx, 6Bh ; 'k'
0x180008b06  mov     r9d, ebx
0x180008b09  call    WPP_SF_d
0x180008b0e  jmp     short loc_180008AB2
0x180008b10  mov     rcx, [rcx+10h]
0x180008b14  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180008b1b  mov     edx, 6Ah ; 'j'
0x180008b20  call    WPP_SF_
0x180008b25  jmp     loc_180008A80
```
