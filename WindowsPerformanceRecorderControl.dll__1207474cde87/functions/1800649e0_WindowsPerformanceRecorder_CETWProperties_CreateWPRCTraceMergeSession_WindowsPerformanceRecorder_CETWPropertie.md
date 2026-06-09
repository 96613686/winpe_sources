# WindowsPerformanceRecorder::CETWProperties::CreateWPRCTraceMergeSession(WindowsPerformanceRecorder::CETWProperties::CEventSession * *,ushort const *,ushort const *,bool)

- ea: `0x1800649e0`
- end: `0x180064bb4`
- name: `?CreateWPRCTraceMergeSession@CETWProperties@WindowsPerformanceRecorder@@SAJPEAPEAUCEventSession@12@PEBG1_N@Z`
- size: `468`
- prototype: `__int64 __fastcall(struct WindowsPerformanceRecorder::CETWProperties::CEventSession **, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180059e74`

## callees

- `0x180013f6c`
- `0x18001e6e0`
- `0x18004ece0`
- `0x18004fa70`
- `0x1800649e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180064a21`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180064a21`

## string_xrefs

- `0x180064a33`: `COMGUARD`
- `0x180064a42`: `CreateWPRCTraceMergeSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WindowsPerformanceRecorder::CETWProperties::CreateWPRCTraceMergeSession(
        struct WindowsPerformanceRecorder::CETWProperties::CEventSession **a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int8 a4)
{
  int v5; // r15d
  signed int ETWSession; // ebx
  __int64 v9; // r8
  __int64 v11; // rcx
  int Format; // [rsp+20h] [rbp-E0h]
  const char *v13; // [rsp+28h] [rbp-D8h]
  int Data3; // [rsp+28h] [rbp-D8h]
  int v15; // [rsp+30h] [rbp-D0h]
  int v16; // [rsp+38h] [rbp-C8h]
  int v17; // [rsp+40h] [rbp-C0h]
  int v18; // [rsp+48h] [rbp-B8h]
  int v19; // [rsp+50h] [rbp-B0h]
  int v20; // [rsp+58h] [rbp-A8h]
  int v21; // [rsp+60h] [rbp-A0h]
  int v22; // [rsp+68h] [rbp-98h]
  GUID pguid; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v24[3]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Buffer[40]; // [rsp+B0h] [rbp-50h] BYREF

  v5 = a4;
  pguid = 0;
  ETWSession = CoCreateGuid(&pguid);
  if ( ETWSession < 0 )
  {
    v9 = 1086;
LABEL_3:
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      (unsigned __int8)"CreateWPRCTraceMergeSession",
      (const char *)v9,
      ETWSession,
      "COMGUARD",
      v13);
    return (unsigned int)ETWSession;
  }
  v22 = pguid.Data4[7];
  v21 = pguid.Data4[6];
  v20 = pguid.Data4[5];
  v19 = pguid.Data4[4];
  v18 = pguid.Data4[3];
  v17 = pguid.Data4[2];
  v16 = pguid.Data4[1];
  v24[0] = *(_OWORD *)&WindowsPerformanceRecorder::CETWProperties::sc_WPRCTraceMergeSessionPrefix;
  v15 = pguid.Data4[0];
  Data3 = pguid.Data3;
  Format = pguid.Data2;
  v24[1] = xmmword_18009C4E0;
  v24[2] = xmmword_18009C4F0;
  swprintf_s(
    Buffer,
    0x25u,
    L"%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x",
    pguid.Data1,
    Format,
    Data3,
    v15,
    v16,
    v17,
    v18,
    v19,
    v20,
    v21,
    v22);
  ETWSession = WindowsPerformanceRecorder::CETWProperties::CreateETWSession(
                 v24,
                 (__int64)a2,
                 2,
                 0,
                 (__int64)a1,
                 (__int64)a3,
                 v5,
                 0);
  if ( ETWSession < 0 )
  {
    v9 = 1093;
    goto LABEL_3;
  }
  *(_DWORD *)(*((_QWORD *)*a1 + 1) + 72LL) = 0;
  *(_DWORD *)(*((_QWORD *)*a1 + 1) + 64LL) |= 0x1000000u;
  *(_DWORD *)(*((_QWORD *)*a1 + 1) + 48LL) = 128;
  *(_DWORD *)(*((_QWORD *)*a1 + 1) + 56LL) = 64;
  *(_DWORD *)(*((_QWORD *)*a1 + 1) + 52LL) = 64;
  v11 = *((_QWORD *)*a1 + 2);
  if ( v11 )
  {
    *(_DWORD *)(v11 + 136) &= ~2u;
    *(_DWORD *)(v11 + 136) |= 2 * v5;
  }
  return 0;
}

```

## disassembly

```asm
0x1800649e0  push    rbp
0x1800649e2  push    rbx
0x1800649e3  push    rsi
0x1800649e4  push    rdi
0x1800649e5  push    r12
0x1800649e7  push    r13
0x1800649e9  push    r14
0x1800649eb  push    r15
0x1800649ed  lea     rbp, [rsp-18h]
0x1800649f2  sub     rsp, 118h
0x1800649f9  mov     rax, cs:__security_cookie
0x180064a00  xor     rax, rsp
0x180064a03  mov     [rbp+50h+var_50], rax
0x180064a07  mov     r14, rcx
0x180064a0a  movzx   r15d, r9b
0x180064a0e  xorps   xmm0, xmm0
0x180064a11  lea     rcx, [rsp+150h+pguid]; pguid
0x180064a16  movups  xmmword ptr [rsp+150h+pguid.Data1], xmm0
0x180064a1b  mov     r13, r8
0x180064a1e  mov     r12, rdx
0x180064a21  call    cs:__imp_CoCreateGuid
0x180064a27  mov     ebx, eax
0x180064a29  test    eax, eax
0x180064a2b  jns     short loc_180064A5A
0x180064a2d  mov     r8d, 43Eh; char *
0x180064a33  lea     rcx, aComguard; "COMGUARD"
0x180064a3a  mov     r9d, ebx; unsigned int
0x180064a3d  mov     [rsp+150h+Format], rcx; Format
0x180064a42  lea     rdx, aCreatewprctrac; "CreateWPRCTraceMergeSession"
0x180064a49  mov     ecx, 2; this
0x180064a4e  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180064a53  mov     eax, ebx
0x180064a55  jmp     loc_180064B94
0x180064a5a  movzx   ecx, [rsp+150h+pguid.Data4+6]
0x180064a5f  movups  xmm0, cs:?sc_WPRCTraceMergeSessionPrefix@CETWProperties@WindowsPerformanceRecorder@@0QBGB; ushort const near * const WindowsPerformanceRecorder::CETWProperties::sc_WPRCTraceMergeSessionPrefix
0x180064a66  movzx   edx, [rsp+150h+pguid.Data4+5]
0x180064a6b  movzx   r8d, [rsp+150h+pguid.Data4+4]
0x180064a71  movzx   r9d, [rsp+150h+pguid.Data4+3]
0x180064a77  movzx   eax, [rsp+150h+pguid.Data4+7]
0x180064a7c  movzx   r10d, [rsp+150h+pguid.Data4+2]
0x180064a82  movzx   r11d, [rsp+150h+pguid.Data4+1]
0x180064a88  movups  xmm1, cs:xmmword_18009C4E0
0x180064a8f  movzx   ebx, [rsp+150h+pguid.Data4]
0x180064a94  movzx   edi, [rsp+150h+pguid.Data3]
0x180064a99  movzx   esi, [rsp+150h+pguid.Data2]
0x180064a9e  mov     [rsp+150h+var_E8], eax
0x180064aa2  mov     [rsp+150h+var_F0], ecx
0x180064aa6  lea     rcx, [rbp+50h+Buffer]; Buffer
0x180064aaa  mov     [rsp+150h+var_F8], edx
0x180064aae  mov     edx, 25h ; '%'; BufferCount
0x180064ab3  mov     [rsp+150h+var_100], r8d
0x180064ab8  lea     r8, a08x04x04x02x02_0; "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02"...
0x180064abf  mov     [rsp+150h+var_108], r9d
0x180064ac4  mov     r9d, [rsp+150h+pguid.Data1]
0x180064ac9  mov     [rsp+150h+var_110], r10d
0x180064ace  mov     dword ptr [rsp+150h+var_118], r11d
0x180064ad3  movaps  [rbp+50h+var_D0], xmm0
0x180064ad7  movups  xmm0, cs:xmmword_18009C4F0
0x180064ade  mov     [rsp+150h+var_120], ebx
0x180064ae2  mov     dword ptr [rsp+150h+var_128], edi
0x180064ae6  mov     dword ptr [rsp+150h+Format], esi
0x180064aea  movaps  [rbp+50h+var_C0], xmm1
0x180064aee  movaps  [rbp+50h+var_B0], xmm0
0x180064af2  call    swprintf_s
0x180064af7  mov     [rsp+150h+var_118], 0
0x180064b00  lea     rcx, [rbp+50h+var_D0]
0x180064b04  xor     r9d, r9d
0x180064b07  mov     byte ptr [rsp+150h+var_120], r15b
0x180064b0c  mov     [rsp+150h+var_128], r13
0x180064b11  mov     rdx, r12
0x180064b14  mov     [rsp+150h+Format], r14
0x180064b19  lea     r8d, [r9+2]
0x180064b1d  call    ?CreateETWSession@CETWProperties@WindowsPerformanceRecorder@@CAJPEBG0W4__MIDL_IProfile_0001@@_KPEAPEAUCEventSession@12@0_N0@Z; WindowsPerformanceRecorder::CETWProperties::CreateETWSession(ushort const *,ushort const *,__MIDL_IProfile_0001,unsigned __int64,WindowsPerformanceRecorder::CETWProperties::CEventSession * *,ushort const *,bool,ushort const *)
0x180064b22  mov     ebx, eax
0x180064b24  test    eax, eax
0x180064b26  jns     short loc_180064B33
0x180064b28  mov     r8d, 445h
0x180064b2e  jmp     loc_180064A33
0x180064b33  mov     rax, [r14]
0x180064b36  mov     edx, 40h ; '@'
0x180064b3b  mov     rcx, [rax+8]
0x180064b3f  mov     dword ptr [rcx+48h], 0
0x180064b46  mov     rax, [r14]
0x180064b49  mov     rcx, [rax+8]
0x180064b4d  bts     dword ptr [rcx+40h], 18h
0x180064b52  mov     rax, [r14]
0x180064b55  mov     rcx, [rax+8]
0x180064b59  mov     dword ptr [rcx+30h], 80h
0x180064b60  mov     rax, [r14]
0x180064b63  mov     rcx, [rax+8]
0x180064b67  mov     [rcx+38h], edx
0x180064b6a  mov     rax, [r14]
0x180064b6d  mov     rcx, [rax+8]
0x180064b71  mov     [rcx+34h], edx
0x180064b74  mov     rax, [r14]
0x180064b77  mov     rcx, [rax+10h]
0x180064b7b  test    rcx, rcx
0x180064b7e  jz      short loc_180064B92
0x180064b80  and     dword ptr [rcx+88h], 0FFFFFFFDh
0x180064b87  mov     eax, r15d
0x180064b8a  add     eax, eax
0x180064b8c  or      [rcx+88h], eax
0x180064b92  xor     eax, eax
0x180064b94  mov     rcx, [rbp+50h+var_50]
0x180064b98  xor     rcx, rsp; StackCookie
0x180064b9b  call    __security_check_cookie
0x180064ba0  add     rsp, 118h
0x180064ba7  pop     r15
0x180064ba9  pop     r14
0x180064bab  pop     r13
0x180064bad  pop     r12
0x180064baf  pop     rdi
0x180064bb0  pop     rsi
0x180064bb1  pop     rbx
0x180064bb2  pop     rbp
0x180064bb3  retn
```
