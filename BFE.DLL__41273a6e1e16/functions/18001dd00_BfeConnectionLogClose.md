# BfeConnectionLogClose

- ea: `0x18001dd00`
- end: `0x18001df4a`
- name: `BfeConnectionLogClose`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001dc3c`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x18001d8b4`
- `0x18001dd00`
- `0x18001df50`
- `0x18005aa60`
- `0x18005b4fc`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001ded8`
- `ntdll!EtwEventWrite` at `0x18001ded8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001dd92`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001dd92`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001dd81`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001dd81`

## string_xrefs

- `0x18001deeb`: `EtwEventWrite`

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
  v4 = EtwEventWrite(gBfeConnectionController, BfeConnectionClosed, 14, v11);
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
0x18001dd00  mov     [rsp-8+arg_8], rbx
0x18001dd05  mov     [rsp-8+arg_10], rdi
0x18001dd0a  push    rbp
0x18001dd0b  lea     rbp, [rsp-8F0h]
0x18001dd13  sub     rsp, 9F0h
0x18001dd1a  mov     rax, cs:__security_cookie
0x18001dd21  xor     rax, rsp
0x18001dd24  mov     [rbp+8F0h+var_10], rax
0x18001dd2b  mov     rbx, rcx
0x18001dd2e  mov     edi, 64h ; 'd'
0x18001dd33  mov     r8d, edi; Size
0x18001dd36  lea     rcx, [rbp+8F0h+var_8D0]; void *
0x18001dd3a  xor     edx, edx; Val
0x18001dd3c  call    memset_0
0x18001dd41  mov     r8d, edi; Size
0x18001dd44  lea     rcx, [rbp+8F0h+var_860]; void *
0x18001dd4b  xor     edx, edx; Val
0x18001dd4d  call    memset_0
0x18001dd52  xorps   xmm0, xmm0
0x18001dd55  lea     r8, [rbp+8F0h+var_860]
0x18001dd5c  xorps   xmm1, xmm1
0x18001dd5f  lea     rdx, [rbp+8F0h+var_8D0]
0x18001dd63  mov     rcx, rbx
0x18001dd66  movups  xmmword ptr [rsp+9F0h+SystemTime.wYear], xmm0
0x18001dd6b  movups  xmmword ptr [rsp+9F0h+var_9C0.wYear], xmm1
0x18001dd70  call    BfeConnectionAddressesToStrings
0x18001dd75  lea     rcx, [rbx+98h]; lpFileTime
0x18001dd7c  lea     rdx, [rsp+9F0h+SystemTime]; lpSystemTime
0x18001dd81  call    cs:__imp_FileTimeToSystemTime
0x18001dd88  nop     dword ptr [rax+rax+00h]
0x18001dd8d  lea     rcx, [rsp+9F0h+var_9C0]; lpSystemTime
0x18001dd92  call    cs:__imp_GetSystemTime
0x18001dd99  nop     dword ptr [rax+rax+00h]
0x18001dd9e  lea     rdx, [rbx+60h]
0x18001dda2  mov     [rsp+9F0h+var_9B0], rbx
0x18001dda7  lea     r8, [rbp+8F0h+var_7F0]
0x18001ddae  mov     [rsp+9F0h+var_9A0], rdx
0x18001ddb3  lea     rcx, [rsp+9F0h+var_990]
0x18001ddb8  mov     [rsp+9F0h+var_9A8], 8
0x18001ddc1  xor     edi, edi
0x18001ddc3  mov     [rsp+9F0h+var_998], 4
0x18001ddcc  call    BfeConnectionEventDataAddCredential
0x18001ddd1  lea     rdx, [rbx+70h]
0x18001ddd5  mov     [rsp+9F0h+var_978], 4
0x18001ddde  lea     r8, [rbp+8F0h+var_400]
0x18001dde5  mov     [rsp+9F0h+var_980], rdx
0x18001ddea  lea     rcx, [rbp+8F0h+var_970]
0x18001ddee  call    BfeConnectionEventDataAddCredential
0x18001ddf3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001ddf7  lea     rdx, [rbp+8F0h+var_8D0]
0x18001ddfb  mov     rax, rcx
0x18001ddfe  inc     rax
0x18001de01  cmp     [rdx+rax*2], di
0x18001de05  jnz     short loc_18001DDFE
0x18001de07  lea     eax, ds:2[rax*2]
0x18001de0e  mov     [rbp+8F0h+var_954], edi
0x18001de11  lea     rdx, [rbp+8F0h+var_8D0]
0x18001de15  mov     [rbp+8F0h+var_958], eax
0x18001de18  lea     rax, [rbp+8F0h+var_860]
0x18001de1f  mov     [rbp+8F0h+var_960], rdx
0x18001de23  inc     rcx
0x18001de26  cmp     [rax+rcx*2], di
0x18001de2a  jnz     short loc_18001DE23
0x18001de2c  lea     rax, [rbp+8F0h+var_860]
0x18001de33  mov     [rbp+8F0h+var_944], edi
0x18001de36  mov     [rbp+8F0h+var_950], rax
0x18001de3a  lea     r9, [rsp+9F0h+var_9B0]
0x18001de3f  lea     eax, ds:2[rcx*2]
0x18001de46  mov     [rbp+8F0h+var_938], 10h
0x18001de4e  mov     rcx, cs:gBfeConnectionController
0x18001de55  lea     rdx, BfeConnectionClosed
0x18001de5c  mov     [rbp+8F0h+var_948], eax
0x18001de5f  mov     r8d, 0Eh
0x18001de65  mov     rax, [rbx+30h]
0x18001de69  mov     [rbp+8F0h+var_940], rax
0x18001de6d  lea     rax, [rbx+38h]
0x18001de71  mov     [rbp+8F0h+var_930], rax
0x18001de75  lea     rax, [rbx+80h]
0x18001de7c  mov     [rbp+8F0h+var_920], rax
0x18001de80  lea     rax, [rbx+88h]
0x18001de87  mov     [rbp+8F0h+var_910], rax
0x18001de8b  lea     rax, [rbx+90h]
0x18001de92  mov     [rbp+8F0h+var_900], rax
0x18001de96  lea     rax, [rsp+9F0h+SystemTime]
0x18001de9b  mov     [rbp+8F0h+var_8F0], rax
0x18001de9f  lea     rax, [rsp+9F0h+var_9C0]
0x18001dea4  mov     [rbp+8F0h+var_8E0], rax
0x18001dea8  mov     [rbp+8F0h+var_928], 4
0x18001deb0  mov     [rbp+8F0h+var_918], 8
0x18001deb8  mov     [rbp+8F0h+var_908], 8
0x18001dec0  mov     [rbp+8F0h+var_8F8], 8
0x18001dec8  mov     [rbp+8F0h+var_8E8], 10h
0x18001ded0  mov     [rbp+8F0h+var_8D8], 10h
0x18001ded8  call    cs:__imp_EtwEventWrite
0x18001dedf  nop     dword ptr [rax+rax+00h]
0x18001dee4  test    eax, eax
0x18001dee6  jz      short loc_18001DF1F
0x18001dee8  mov     r8d, eax
0x18001deeb  lea     rdx, aEtweventwrite; "EtwEventWrite"
0x18001def2  call    WfpReportSysErrorAsWinError
0x18001def7  mov     rbx, rax
0x18001defa  test    rax, rax
0x18001defd  jz      short loc_18001DF22
0x18001deff  lea     rdx, aBfeconnectionl_1; "BfeConnectionLog"
0x18001df06  mov     rcx, rax
0x18001df09  call    WfpReportError
0x18001df0e  lea     rdx, aBfeconnectionl; "BfeConnectionLogClose"
0x18001df15  mov     rcx, rbx
0x18001df18  call    WfpReportError
0x18001df1d  jmp     short loc_18001DF22
0x18001df1f  mov     rbx, rdi
0x18001df22  mov     rax, rbx
0x18001df25  mov     rcx, [rbp+8F0h+var_10]
0x18001df2c  xor     rcx, rsp; StackCookie
0x18001df2f  call    __security_check_cookie
0x18001df34  lea     r11, [rsp+9F0h+var_s0]
0x18001df3c  mov     rbx, [r11+18h]
0x18001df40  mov     rdi, [r11+20h]
0x18001df44  mov     rsp, r11
0x18001df47  pop     rbp
0x18001df48  retn
```
