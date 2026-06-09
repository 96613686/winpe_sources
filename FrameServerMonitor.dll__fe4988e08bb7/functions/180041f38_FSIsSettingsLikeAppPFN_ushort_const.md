# FSIsSettingsLikeAppPFN(ushort const *)

- ea: `0x180041f38`
- end: `0x180042033`
- name: `?FSIsSettingsLikeAppPFN@@YA_NPEBG@Z`
- size: `251`
- prototype: `char __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009c78`

## callees

- `0x180006a98`
- `0x180017e78`
- `0x180041f38`
- `0x180042ffc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041fdc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041fdc`

## pseudocode

```c
char __fastcall FSIsSettingsLikeAppPFN(LPCWCH lpString1)
{
  char v2; // bl
  __int64 v3; // rdi
  int v4; // edx
  int v5; // r8d

  if ( lpString1 )
  {
    v3 = 0;
    while ( CompareStringOrdinal(lpString1, -1, off_180050440[v3], -1, 1) != 2 )
    {
      v2 = 0;
      if ( (unsigned __int64)++v3 >= 4 )
        goto LABEL_11;
    }
    v2 = 1;
LABEL_11:
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      WPP_SF_DdS(*((_QWORD *)WPP_GLOBAL_Control + 27), v4, v5, 0, v2, (__int64)lpString1);
  }
  else
  {
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        157,
        &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids,
        0,
        -2147024809);
    v2 = 0;
    if ( byte_18005E5A5 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        159,
        &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids,
        2147942487LL,
        0);
  }
  return v2;
}

```

## disassembly

```asm
0x180041f38  mov     [rsp+arg_0], rbx
0x180041f3d  mov     [rsp+arg_8], rsi
0x180041f42  push    rdi
0x180041f43  sub     rsp, 30h
0x180041f47  mov     rsi, rcx
0x180041f4a  test    rcx, rcx
0x180041f4d  jnz     short loc_180041FBD
0x180041f4f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180041f56  jb      short loc_180041F7F
0x180041f58  mov     rcx, cs:WPP_GLOBAL_Control
0x180041f5f  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x180041f66  mov     edx, 9Dh
0x180041f6b  mov     [rsp+38h+bIgnoreCase], 80070057h
0x180041f73  xor     r9d, r9d
0x180041f76  mov     rcx, [rcx+10h]
0x180041f7a  call    WPP_SF_qD
0x180041f7f  xor     bl, bl
0x180041f81  cmp     cs:byte_18005E5A5, 1
0x180041f88  jb      loc_180042021
0x180041f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180041f95  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x180041f9c  mov     edx, 9Fh
0x180041fa1  mov     [rsp+38h+bIgnoreCase], 0
0x180041fa9  mov     r9d, 80070057h
0x180041faf  mov     rcx, [rcx+0D8h]
0x180041fb6  call    WPP_SF_Dd
0x180041fbb  jmp     short loc_180042021
0x180041fbd  xor     edi, edi
0x180041fbf  or      r9d, 0FFFFFFFFh; cchCount2
0x180041fc3  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180041fcb  lea     r8, off_180050440; "pfn:MicrosoftWindows.Client.CopilotFram"...
0x180041fd2  or      edx, r9d; cchCount1
0x180041fd5  mov     r8, [r8+rdi*8]; lpString2
0x180041fd9  mov     rcx, rsi; lpString1
0x180041fdc  call    cs:__imp_CompareStringOrdinal
0x180041fe2  cmp     eax, 2
0x180041fe5  jz      short loc_180041FF4
0x180041fe7  xor     bl, bl
0x180041fe9  inc     rdi
0x180041fec  cmp     rdi, 4
0x180041ff0  jb      short loc_180041FBF
0x180041ff2  jmp     short loc_180041FF6
0x180041ff4  mov     bl, 1
0x180041ff6  cmp     cs:byte_18005E5A5, 8
0x180041ffd  jb      short loc_180042021
0x180041fff  movzx   ecx, bl
0x180042002  xor     r9d, r9d
0x180042005  mov     [rsp+38h+var_10], rsi
0x18004200a  mov     [rsp+38h+bIgnoreCase], ecx
0x18004200e  mov     rcx, cs:WPP_GLOBAL_Control
0x180042015  mov     rcx, [rcx+0D8h]
0x18004201c  call    WPP_SF_DdS
0x180042021  mov     rsi, [rsp+38h+arg_8]
0x180042026  mov     al, bl
0x180042028  mov     rbx, [rsp+38h+arg_0]
0x18004202d  add     rsp, 30h
0x180042031  pop     rdi
0x180042032  retn
```
