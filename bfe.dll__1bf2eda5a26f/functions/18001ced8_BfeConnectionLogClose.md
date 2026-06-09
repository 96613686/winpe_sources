# BfeConnectionLogClose

- ea: `0x18001ced8`
- end: `0x18001d10f`
- name: `BfeConnectionLogClose`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001ce20`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x18001c87c`
- `0x18001ced8`
- `0x18001d118`
- `0x180058b30`
- `0x1800595ac`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001d0a4`
- `ntdll!EtwEventWrite` at `0x18001d0a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001cf64`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001cf64`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001cf59`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001cf59`

## string_xrefs

- `0x18001d0b1`: `EtwEventWrite`

## pseudocode

```c
__int64 __fastcall BfeConnectionLogClose(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  unsigned int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rbx
  _SYSTEMTIME SystemTime; // [rsp+20h] [rbp-E0h] BYREF
  struct _SYSTEMTIME v10; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v11[4]; // [rsp+40h] [rbp-C0h] BYREF
  char v12[16]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v13; // [rsp+70h] [rbp-90h]
  __int64 v14; // [rsp+78h] [rbp-88h]
  char v15[16]; // [rsp+80h] [rbp-80h] BYREF
  _WORD *v16; // [rsp+90h] [rbp-70h]
  int v17; // [rsp+98h] [rbp-68h]
  int v18; // [rsp+9Ch] [rbp-64h]
  _WORD *v19; // [rsp+A0h] [rbp-60h]
  int v20; // [rsp+A8h] [rbp-58h]
  int v21; // [rsp+ACh] [rbp-54h]
  __int64 v22; // [rsp+B0h] [rbp-50h]
  __int64 v23; // [rsp+B8h] [rbp-48h]
  __int64 v24; // [rsp+C0h] [rbp-40h]
  __int64 v25; // [rsp+C8h] [rbp-38h]
  __int64 v26; // [rsp+D0h] [rbp-30h]
  __int64 v27; // [rsp+D8h] [rbp-28h]
  __int64 v28; // [rsp+E0h] [rbp-20h]
  __int64 v29; // [rsp+E8h] [rbp-18h]
  __int64 v30; // [rsp+F0h] [rbp-10h]
  __int64 v31; // [rsp+F8h] [rbp-8h]
  _SYSTEMTIME *p_SystemTime; // [rsp+100h] [rbp+0h]
  __int64 v33; // [rsp+108h] [rbp+8h]
  struct _SYSTEMTIME *v34; // [rsp+110h] [rbp+10h]
  __int64 v35; // [rsp+118h] [rbp+18h]
  _WORD v36[56]; // [rsp+120h] [rbp+20h] BYREF
  _WORD v37[56]; // [rsp+190h] [rbp+90h] BYREF
  char v38[1008]; // [rsp+200h] [rbp+100h] BYREF
  char v39[1008]; // [rsp+5F0h] [rbp+4F0h] BYREF

  memset_0(v36, 0, 0x64u);
  memset_0(v37, 0, 0x64u);
  SystemTime = 0;
  v10 = 0;
  BfeConnectionAddressesToStrings(a1, v36, v37);
  FileTimeToSystemTime((const FILETIME *)(a1 + 152), &SystemTime);
  GetSystemTime(&v10);
  v11[0] = a1;
  v11[2] = a1 + 96;
  v11[1] = 8;
  v11[3] = 4;
  BfeConnectionEventDataAddCredential(v12, a1 + 96, v38);
  v14 = 4;
  v13 = a1 + 112;
  BfeConnectionEventDataAddCredential(v15, a1 + 112, v39);
  v2 = -1;
  v3 = -1;
  do
    ++v3;
  while ( v36[v3] );
  v18 = 0;
  v17 = 2 * v3 + 2;
  v16 = v36;
  do
    ++v2;
  while ( v37[v2] );
  v21 = 0;
  v19 = v37;
  v23 = 16;
  v20 = 2 * v2 + 2;
  v22 = *(_QWORD *)(a1 + 48);
  v24 = a1 + 56;
  v26 = a1 + 128;
  v28 = a1 + 136;
  v30 = a1 + 144;
  p_SystemTime = &SystemTime;
  v34 = &v10;
  v25 = 4;
  v27 = 8;
  v29 = 8;
  v31 = 8;
  v33 = 16;
  v35 = 16;
  v4 = EtwEventWrite(qword_1800F2668[219], BfeConnectionClosed, 14, v11);
  if ( !v4 )
    return 0;
  v6 = WfpReportSysErrorAsWinError(v5, "EtwEventWrite", v4);
  v7 = v6;
  if ( v6 )
  {
    WfpReportError(v6, "BfeConnectionLog");
    WfpReportError(v7, "BfeConnectionLogClose");
  }
  return v7;
}

```

## disassembly

```asm
0x18001ced8  mov     [rsp-8+arg_8], rbx
0x18001cedd  mov     [rsp-8+arg_10], rdi
0x18001cee2  push    rbp
0x18001cee3  lea     rbp, [rsp-8F0h]
0x18001ceeb  sub     rsp, 9F0h
0x18001cef2  mov     rax, cs:__security_cookie
0x18001cef9  xor     rax, rsp
0x18001cefc  mov     [rbp+8F0h+var_10], rax
0x18001cf03  mov     rbx, rcx
0x18001cf06  mov     edi, 64h ; 'd'
0x18001cf0b  mov     r8d, edi; Size
0x18001cf0e  lea     rcx, [rbp+8F0h+var_8D0]; void *
0x18001cf12  xor     edx, edx; Val
0x18001cf14  call    memset_0
0x18001cf19  mov     r8d, edi; Size
0x18001cf1c  lea     rcx, [rbp+8F0h+var_860]; void *
0x18001cf23  xor     edx, edx; Val
0x18001cf25  call    memset_0
0x18001cf2a  xorps   xmm0, xmm0
0x18001cf2d  lea     r8, [rbp+8F0h+var_860]
0x18001cf34  xorps   xmm1, xmm1
0x18001cf37  lea     rdx, [rbp+8F0h+var_8D0]
0x18001cf3b  mov     rcx, rbx
0x18001cf3e  movups  xmmword ptr [rsp+9F0h+SystemTime.wYear], xmm0
0x18001cf43  movups  xmmword ptr [rsp+9F0h+var_9C0.wYear], xmm1
0x18001cf48  call    BfeConnectionAddressesToStrings
0x18001cf4d  lea     rcx, [rbx+98h]; lpFileTime
0x18001cf54  lea     rdx, [rsp+9F0h+SystemTime]; lpSystemTime
0x18001cf59  call    cs:__imp_FileTimeToSystemTime
0x18001cf5f  lea     rcx, [rsp+9F0h+var_9C0]; lpSystemTime
0x18001cf64  call    cs:__imp_GetSystemTime
0x18001cf6a  lea     rdx, [rbx+60h]
0x18001cf6e  mov     [rsp+9F0h+var_9B0], rbx
0x18001cf73  lea     r8, [rbp+8F0h+var_7F0]
0x18001cf7a  mov     [rsp+9F0h+var_9A0], rdx
0x18001cf7f  lea     rcx, [rsp+9F0h+var_990]
0x18001cf84  mov     [rsp+9F0h+var_9A8], 8
0x18001cf8d  xor     edi, edi
0x18001cf8f  mov     [rsp+9F0h+var_998], 4
0x18001cf98  call    BfeConnectionEventDataAddCredential
0x18001cf9d  lea     rdx, [rbx+70h]
0x18001cfa1  mov     [rsp+9F0h+var_978], 4
0x18001cfaa  lea     r8, [rbp+8F0h+var_400]
0x18001cfb1  mov     [rsp+9F0h+var_980], rdx
0x18001cfb6  lea     rcx, [rbp+8F0h+var_970]
0x18001cfba  call    BfeConnectionEventDataAddCredential
0x18001cfbf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001cfc3  lea     rdx, [rbp+8F0h+var_8D0]
0x18001cfc7  mov     rax, rcx
0x18001cfca  inc     rax
0x18001cfcd  cmp     [rdx+rax*2], di
0x18001cfd1  jnz     short loc_18001CFCA
0x18001cfd3  lea     eax, ds:2[rax*2]
0x18001cfda  mov     [rbp+8F0h+var_954], edi
0x18001cfdd  lea     rdx, [rbp+8F0h+var_8D0]
0x18001cfe1  mov     [rbp+8F0h+var_958], eax
0x18001cfe4  lea     rax, [rbp+8F0h+var_860]
0x18001cfeb  mov     [rbp+8F0h+var_960], rdx
0x18001cfef  inc     rcx
0x18001cff2  cmp     [rax+rcx*2], di
0x18001cff6  jnz     short loc_18001CFEF
0x18001cff8  lea     rax, [rbp+8F0h+var_860]
0x18001cfff  mov     [rbp+8F0h+var_944], edi
0x18001d002  mov     [rbp+8F0h+var_950], rax
0x18001d006  lea     r9, [rsp+9F0h+var_9B0]
0x18001d00b  lea     eax, ds:2[rcx*2]
0x18001d012  mov     [rbp+8F0h+var_938], 10h
0x18001d01a  mov     rcx, cs:qword_1800F2668+6D8h
0x18001d021  lea     rdx, BfeConnectionClosed
0x18001d028  mov     [rbp+8F0h+var_948], eax
0x18001d02b  mov     r8d, 0Eh
0x18001d031  mov     rax, [rbx+30h]
0x18001d035  mov     [rbp+8F0h+var_940], rax
0x18001d039  lea     rax, [rbx+38h]
0x18001d03d  mov     [rbp+8F0h+var_930], rax
0x18001d041  lea     rax, [rbx+80h]
0x18001d048  mov     [rbp+8F0h+var_920], rax
0x18001d04c  lea     rax, [rbx+88h]
0x18001d053  mov     [rbp+8F0h+var_910], rax
0x18001d057  lea     rax, [rbx+90h]
0x18001d05e  mov     [rbp+8F0h+var_900], rax
0x18001d062  lea     rax, [rsp+9F0h+SystemTime]
0x18001d067  mov     [rbp+8F0h+var_8F0], rax
0x18001d06b  lea     rax, [rsp+9F0h+var_9C0]
0x18001d070  mov     [rbp+8F0h+var_8E0], rax
0x18001d074  mov     [rbp+8F0h+var_928], 4
0x18001d07c  mov     [rbp+8F0h+var_918], 8
0x18001d084  mov     [rbp+8F0h+var_908], 8
0x18001d08c  mov     [rbp+8F0h+var_8F8], 8
0x18001d094  mov     [rbp+8F0h+var_8E8], 10h
0x18001d09c  mov     [rbp+8F0h+var_8D8], 10h
0x18001d0a4  call    cs:__imp_EtwEventWrite
0x18001d0aa  test    eax, eax
0x18001d0ac  jz      short loc_18001D0E5
0x18001d0ae  mov     r8d, eax
0x18001d0b1  lea     rdx, aEtweventwrite; "EtwEventWrite"
0x18001d0b8  call    WfpReportSysErrorAsWinError
0x18001d0bd  mov     rbx, rax
0x18001d0c0  test    rax, rax
0x18001d0c3  jz      short loc_18001D0E8
0x18001d0c5  lea     rdx, aBfeconnectionl_1; "BfeConnectionLog"
0x18001d0cc  mov     rcx, rax
0x18001d0cf  call    WfpReportError
0x18001d0d4  lea     rdx, aBfeconnectionl; "BfeConnectionLogClose"
0x18001d0db  mov     rcx, rbx
0x18001d0de  call    WfpReportError
0x18001d0e3  jmp     short loc_18001D0E8
0x18001d0e5  mov     rbx, rdi
0x18001d0e8  mov     rax, rbx
0x18001d0eb  mov     rcx, [rbp+8F0h+var_10]
0x18001d0f2  xor     rcx, rsp; StackCookie
0x18001d0f5  call    __security_check_cookie
0x18001d0fa  lea     r11, [rsp+9F0h+var_s0]
0x18001d102  mov     rbx, [r11+18h]
0x18001d106  mov     rdi, [r11+20h]
0x18001d10a  mov     rsp, r11
0x18001d10d  pop     rbp
0x18001d10e  retn
```
