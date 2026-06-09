# HttpCreateClientCredential

- ea: `0x180005ab0`
- end: `0x180005c64`
- name: `HttpCreateClientCredential`
- size: `436`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180002b40`
- `0x180005ab0`
- `0x18000a5f0`
- `0x18000b080`
- `0x18000b0b8`
- `0x18000bce0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180005bb7`
- `ntdll!RtlNtStatusToDosError` at `0x180005bb7`
- `ntdll!RtlInitUnicodeStringEx` at `0x180005bab`
- `ntdll!RtlInitUnicodeStringEx` at `0x180005bab`

## pseudocode

```c
__int64 __fastcall HttpCreateClientCredential(HANDLE FileHandle, __int128 *a2, const WCHAR *a3, __int64 a4, _QWORD *a5)
{
  ULONG v9; // ebx
  __int128 v10; // xmm0
  int v11; // eax
  int inited; // eax
  __int64 v13; // rcx
  __int64 v14; // r9
  __int64 v16; // [rsp+40h] [rbp-41h] BYREF
  __int64 v17; // [rsp+48h] [rbp-39h] BYREF
  _QWORD v18[2]; // [rsp+50h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-21h] BYREF
  __int128 v20; // [rsp+70h] [rbp-11h]
  __int128 v21; // [rsp+80h] [rbp-1h]

  DestinationString = 0;
  v20 = 0;
  v21 = 0;
  v17 = 0;
  LODWORD(v16) = 0;
  if ( (byte_1800126A3 & 4) != 0 )
  {
    v18[1] = 20;
    v18[0] = a2;
    WPP_SF_q_HEX_Si((_DWORD)FileHandle, (_DWORD)a2, (_DWORD)a3, (_DWORD)FileHandle, (__int64)v18, (__int64)a3, a4);
  }
  if ( !a5 )
    goto LABEL_4;
  *a5 = 0;
  if ( (a4 & 0xFFFFFFFFFFFFFE0EuLL) != 0 || !g_KirAddDisableAiaFlag && (a4 & 0x100) != 0 )
    goto LABEL_4;
  if ( (a4 & 1) != 0 )
  {
    if ( !a2 && !a3 )
    {
      *((_QWORD *)&v21 + 1) = a4;
      goto LABEL_17;
    }
LABEL_4:
    v9 = 87;
    goto LABEL_20;
  }
  if ( !a2 || !a3 )
    goto LABEL_4;
  v10 = *a2;
  v11 = *((_DWORD *)a2 + 4);
  *((_QWORD *)&v21 + 1) = a4;
  v20 = v10;
  LODWORD(v21) = v11;
  inited = RtlInitUnicodeStringEx(&DestinationString, a3);
  if ( inited < 0 )
  {
    v9 = RtlNtStatusToDosError(inited);
    goto LABEL_20;
  }
  if ( DestinationString.Length >= 0x100u )
    goto LABEL_4;
LABEL_17:
  v9 = HttpApiSynchronousDeviceControl(FileHandle, 0x1240F0u, &DestinationString, 0x30u, &v17, 8u, (__int64)&v16);
  if ( !v9 )
  {
    v14 = v17;
    *a5 = v17;
    if ( (byte_1800126A3 & 4) == 0 )
      return v9;
    WPP_SF_I(v13, 50, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids, v14);
  }
LABEL_20:
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_d(1050, 51, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180005ab0  push    rbp
0x180005ab2  push    rbx
0x180005ab3  push    rsi
0x180005ab4  push    rdi
0x180005ab5  push    r13
0x180005ab7  push    r14
0x180005ab9  push    r15
0x180005abb  lea     rbp, [rsp-1Fh]
0x180005ac0  sub     rsp, 0A0h
0x180005ac7  mov     rax, cs:__security_cookie
0x180005ace  xor     rax, rsp
0x180005ad1  mov     [rbp+4Fh+var_40], rax
0x180005ad5  mov     r14, [rbp+4Fh+arg_20]
0x180005ad9  xorps   xmm0, xmm0
0x180005adc  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x180005ae0  mov     rbx, r9
0x180005ae3  mov     rsi, r8
0x180005ae6  movups  [rbp+4Fh+var_60], xmm0
0x180005aea  mov     rdi, rdx
0x180005aed  mov     r15, rcx
0x180005af0  movups  [rbp+4Fh+var_50], xmm0
0x180005af4  mov     [rbp+4Fh+var_88], 0
0x180005afc  mov     dword ptr [rbp+4Fh+var_90], 0
0x180005b03  test    cs:byte_1800126A3, 4
0x180005b0a  jz      short loc_180005B41
0x180005b0c  movups  [rbp+4Fh+var_80], xmm0
0x180005b10  mov     qword ptr [rbp+4Fh+var_80], rdx
0x180005b14  mov     eax, 14h
0x180005b19  mov     word ptr [rbp+4Fh+var_80+8], ax
0x180005b1d  mov     r9, rcx
0x180005b20  movaps  xmm0, [rbp+4Fh+var_80]
0x180005b24  lea     rax, [rbp+4Fh+var_80]
0x180005b28  mov     [rsp+0D0h+var_A0], rbx
0x180005b2d  mov     qword ptr [rsp+0D0h+var_A8], r8
0x180005b32  movdqa  [rbp+4Fh+var_80], xmm0
0x180005b37  mov     [rsp+0D0h+var_B0], rax
0x180005b3c  call    WPP_SF_q_HEX_Si
0x180005b41  test    r14, r14
0x180005b44  jnz     short loc_180005B50
0x180005b46  mov     ebx, 57h ; 'W'
0x180005b4b  jmp     loc_180005C22
0x180005b50  mov     qword ptr [r14], 0
0x180005b57  test    rbx, 0FFFFFFFFFFFFFE0Eh
0x180005b5e  jnz     short loc_180005B46
0x180005b60  cmp     cs:g_KirAddDisableAiaFlag, 0
0x180005b67  mov     r13d, 100h
0x180005b6d  jnz     short loc_180005B74
0x180005b6f  test    r13, rbx
0x180005b72  jnz     short loc_180005B46
0x180005b74  test    bl, 1
0x180005b77  jz      short loc_180005B89
0x180005b79  test    rdi, rdi
0x180005b7c  jnz     short loc_180005B46
0x180005b7e  test    rsi, rsi
0x180005b81  jnz     short loc_180005B46
0x180005b83  mov     qword ptr [rbp+4Fh+var_50+8], rbx
0x180005b87  jmp     short loc_180005BCC
0x180005b89  test    rdi, rdi
0x180005b8c  jz      short loc_180005B46
0x180005b8e  test    rsi, rsi
0x180005b91  jz      short loc_180005B46
0x180005b93  movups  xmm0, xmmword ptr [rdi]
0x180005b96  mov     eax, [rdi+10h]
0x180005b99  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x180005b9d  mov     rdx, rsi; SourceString
0x180005ba0  mov     qword ptr [rbp+4Fh+var_50+8], rbx
0x180005ba4  movups  [rbp+4Fh+var_60], xmm0
0x180005ba8  mov     dword ptr [rbp+4Fh+var_50], eax
0x180005bab  call    cs:__imp_RtlInitUnicodeStringEx
0x180005bb1  test    eax, eax
0x180005bb3  jns     short loc_180005BC1
0x180005bb5  mov     ecx, eax; Status
0x180005bb7  call    cs:__imp_RtlNtStatusToDosError
0x180005bbd  mov     ebx, eax
0x180005bbf  jmp     short loc_180005C22
0x180005bc1  cmp     [rbp+4Fh+DestinationString.Length], r13w
0x180005bc6  jnb     loc_180005B46
0x180005bcc  lea     rax, [rbp+4Fh+var_90]
0x180005bd0  mov     r9d, 30h ; '0'; InputBufferLength
0x180005bd6  mov     [rsp+0D0h+var_A0], rax; __int64
0x180005bdb  lea     r8, [rbp+4Fh+DestinationString]; InputBuffer
0x180005bdf  lea     rax, [rbp+4Fh+var_88]
0x180005be3  mov     [rsp+0D0h+var_A8], 8; ULONG
0x180005beb  mov     edx, 1240F0h; IoControlCode
0x180005bf0  mov     [rsp+0D0h+var_B0], rax; PVOID
0x180005bf5  mov     rcx, r15; FileHandle
0x180005bf8  call    HttpApiSynchronousDeviceControl
0x180005bfd  mov     ebx, eax
0x180005bff  test    eax, eax
0x180005c01  jnz     short loc_180005C22
0x180005c03  mov     r9, [rbp+4Fh+var_88]
0x180005c07  mov     [r14], r9
0x180005c0a  test    cs:byte_1800126A3, 4
0x180005c11  jz      short loc_180005C44
0x180005c13  lea     edx, [rax+32h]
0x180005c16  lea     r8, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids
0x180005c1d  call    WPP_SF_I
0x180005c22  test    cs:byte_1800126A3, 4
0x180005c29  jz      short loc_180005C44
0x180005c2b  mov     edx, 33h ; '3'
0x180005c30  lea     r8, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids
0x180005c37  mov     ecx, 41Ah
0x180005c3c  mov     r9d, ebx
0x180005c3f  call    WPP_SF_d
0x180005c44  mov     eax, ebx
0x180005c46  mov     rcx, [rbp+4Fh+var_40]
0x180005c4a  xor     rcx, rsp; StackCookie
0x180005c4d  call    __security_check_cookie
0x180005c52  add     rsp, 0A0h
0x180005c59  pop     r15
0x180005c5b  pop     r14
0x180005c5d  pop     r13
0x180005c5f  pop     rdi
0x180005c60  pop     rsi
0x180005c61  pop     rbx
0x180005c62  pop     rbp
0x180005c63  retn
```
