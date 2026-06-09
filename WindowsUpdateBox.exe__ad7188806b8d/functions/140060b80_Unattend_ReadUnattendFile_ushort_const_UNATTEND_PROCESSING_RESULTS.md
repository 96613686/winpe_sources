# Unattend::ReadUnattendFile(ushort const *,_UNATTEND_PROCESSING_RESULTS *)

- ea: `0x140060b80`
- end: `0x140060d97`
- name: `?ReadUnattendFile@Unattend@@QEAAJPEBGPEAU_UNATTEND_PROCESSING_RESULTS@@@Z`
- size: `535`
- prototype: `__int64 __fastcall(Unattend *__hidden this, const unsigned __int16 *, struct _UNATTEND_PROCESSING_RESULTS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14005c35c`

## callees

- `0x14005c0d4`
- `0x14005c92c`
- `0x14005ff00`
- `0x140060b80`
- `0x14006db80`
- `0x140080d70`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x140060bc4`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x140060bc4`
- `ntdll!RtlFreeHeap` at `0x140060d03`
- `ntdll!RtlFreeHeap` at `0x140060d42`
- `ntdll!RtlFreeHeap` at `0x140060d03`
- `ntdll!RtlFreeHeap` at `0x140060d42`
- `ntdll!RtlNtStatusToDosError` at `0x140060c79`
- `ntdll!RtlNtStatusToDosError` at `0x140060d13`
- `ntdll!RtlNtStatusToDosError` at `0x140060d5b`
- `ntdll!RtlNtStatusToDosError` at `0x140060c79`
- `ntdll!RtlNtStatusToDosError` at `0x140060d13`
- `ntdll!RtlNtStatusToDosError` at `0x140060d5b`

## pseudocode

```c
__int64 __fastcall Unattend::ReadUnattendFile(
        Unattend *this,
        const unsigned __int16 *a2,
        struct _UNATTEND_PROCESSING_RESULTS *a3)
{
  NTSTATUS v6; // eax
  bool v7; // r8
  NTSTATUS v8; // eax
  NTSTATUS Microdom; // eax
  signed int v10; // eax
  signed int v11; // ebx
  signed int v12; // eax
  signed int v13; // eax
  _QWORD v15[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v16; // [rsp+30h] [rbp-D0h]
  __int128 v17; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v18; // [rsp+50h] [rbp-B0h]
  PVOID v19[2]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v20[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v21; // [rsp+78h] [rbp-88h]
  __int64 v22; // [rsp+88h] [rbp-78h]
  void ***v23; // [rsp+90h] [rbp-70h]
  __int64 v24; // [rsp+98h] [rbp-68h]
  void **v25; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v26; // [rsp+A8h] [rbp-58h]
  __int64 v27; // [rsp+B0h] [rbp-50h]
  unsigned int v28; // [rsp+B8h] [rbp-48h]
  PVOID P; // [rsp+C0h] [rbp-40h]
  void **v30; // [rsp+D0h] [rbp-30h] BYREF
  void **v31; // [rsp+D8h] [rbp-28h] BYREF
  __m128i si128; // [rsp+E0h] [rbp-20h]
  __int64 v33; // [rsp+F0h] [rbp-10h]
  __int64 v34; // [rsp+F8h] [rbp-8h]
  __int128 v35; // [rsp+100h] [rbp+0h]

  *(_OWORD *)v19 = 0;
  v6 = RtlDosPathNameToNtPathName_U_WithStatus(a2, v19, 0, 0);
  if ( v6 < 0 )
  {
    v13 = RtlNtStatusToDosError(v6);
    v11 = v13;
    if ( v13 > 0 )
      return (unsigned __int16)v13 | 0x80070000;
  }
  else
  {
    v30 = &CFileRtlFOStream::`vftable'{for `Windows::Rtl::IRtlWOFOStream'};
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v31 = &CFileRtlFOStream::`vftable'{for `Windows::Rtl::IRtlROFOStream'};
    v35 = 0;
    v33 = 0;
    v34 = 0;
    v8 = CFileRtlFOStream::Open((CFileRtlFOStream *)&v30, (const unsigned __int16 *)v19[1], v7);
    if ( v8 < 0 )
    {
      v12 = RtlNtStatusToDosError(v8);
      v11 = v12;
      if ( v12 > 0 )
        v11 = (unsigned __int16)v12 | 0x80070000;
    }
    else
    {
      v22 = 0;
      v20[1] = &v31;
      v24 = 0;
      v23 = &v25;
      v26 = 0;
      v25 = &UnattendXmlErrorHandler::`vftable';
      v27 = 0;
      v21 = 0;
      v28 = 1;
      P = 0;
      v20[0] = 1;
      Microdom = RtlCreateMicrodom((__int64)v20, (__int64)this);
      v10 = RtlNtStatusToDosError(Microdom);
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      if ( a3 )
      {
        if ( (_DWORD)v26 )
        {
          v18 = __PAIR64__(v27, HIDWORD(v26));
          v15[0] = 0;
          v16 = 0;
          v15[1] = a2;
          v17 = 0;
          UnattendAddResults(a3, v28, v15);
          if ( *(int *)a3 < 0 && v11 < 0 )
            v11 = 1;
        }
      }
      v25 = &UnattendXmlErrorHandler::`vftable';
      if ( P )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v19[1]);
    CFileRtlFOStream::~CFileRtlFOStream((CFileRtlFOStream *)&v30);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140060b80  push    rbp
0x140060b82  push    rbx
0x140060b83  push    rsi
0x140060b84  push    rdi
0x140060b85  push    r12
0x140060b87  push    r14
0x140060b89  push    r15
0x140060b8b  lea     rbp, [rsp-20h]
0x140060b90  sub     rsp, 120h
0x140060b97  mov     rax, cs:__security_cookie
0x140060b9e  xor     rax, rsp
0x140060ba1  mov     [rbp+50h+var_40], rax
0x140060ba5  mov     rsi, rdx
0x140060ba8  mov     rdi, r8
0x140060bab  mov     rbx, rcx
0x140060bae  lea     rdx, [rsp+150h+var_F8]
0x140060bb3  xorps   xmm0, xmm0
0x140060bb6  mov     rcx, rsi
0x140060bb9  xor     r9d, r9d
0x140060bbc  xor     r8d, r8d
0x140060bbf  movups  xmmword ptr [rsp+150h+var_F8], xmm0
0x140060bc4  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x140060bcb  nop     dword ptr [rax+rax+00h]
0x140060bd0  xor     r14d, r14d
0x140060bd3  test    eax, eax
0x140060bd5  js      loc_140060D59
0x140060bdb  movdqa  xmm0, cs:__xmm@0000000000000000ffffffffffffffff
0x140060be3  lea     rax, ??_7CFileRtlFOStream@@6BIRtlWOFOStream@Rtl@Windows@@@; const CFileRtlFOStream::`vftable'{for `Windows::Rtl::IRtlWOFOStream'}
0x140060bea  mov     rdx, [rsp+150h+var_F8+8]; unsigned __int16 *
0x140060bef  lea     rcx, [rbp+50h+var_80]; this
0x140060bf3  mov     [rbp+50h+var_80], rax
0x140060bf7  lea     rax, ??_7CFileRtlFOStream@@6BIRtlROFOStream@Rtl@Windows@@@; const CFileRtlFOStream::`vftable'{for `Windows::Rtl::IRtlROFOStream'}
0x140060bfe  movdqa  [rbp+50h+var_70], xmm0
0x140060c03  xorps   xmm0, xmm0
0x140060c06  mov     [rbp+50h+var_78], rax
0x140060c0a  movdqu  [rbp+50h+var_50], xmm0
0x140060c0f  mov     [rbp+50h+var_60], r14
0x140060c13  mov     [rbp+50h+var_58], r14
0x140060c17  call    ?Open@CFileRtlFOStream@@QEAAJPEBG_N@Z; CFileRtlFOStream::Open(ushort const *,bool)
0x140060c1c  test    eax, eax
0x140060c1e  js      loc_140060D11
0x140060c24  lea     rax, [rbp+50h+var_78]
0x140060c28  mov     [rbp+50h+var_C8], r14
0x140060c2c  mov     [rsp+150h+var_E0], rax
0x140060c31  lea     r12d, [r14+1]
0x140060c35  lea     rax, [rbp+50h+var_B0]
0x140060c39  mov     [rbp+50h+var_B8], r14
0x140060c3d  xorps   xmm0, xmm0
0x140060c40  mov     [rbp+50h+var_C0], rax
0x140060c44  lea     r15, ??_7UnattendXmlErrorHandler@@6B@; const UnattendXmlErrorHandler::`vftable'
0x140060c4b  mov     [rbp+50h+var_A8], r14
0x140060c4f  mov     rdx, rbx
0x140060c52  mov     [rbp+50h+var_B0], r15
0x140060c56  lea     rcx, [rsp+150h+var_E8]
0x140060c5b  mov     [rbp+50h+var_A0], r14
0x140060c5f  movdqu  [rsp+150h+var_D8], xmm0
0x140060c65  mov     [rbp+50h+var_98], r12d
0x140060c69  mov     [rbp+50h+P], r14
0x140060c6d  mov     [rsp+150h+var_E8], r12
0x140060c72  call    RtlCreateMicrodom
0x140060c77  mov     ecx, eax; Status
0x140060c79  call    cs:__imp_RtlNtStatusToDosError
0x140060c80  nop     dword ptr [rax+rax+00h]
0x140060c85  mov     ebx, eax
0x140060c87  test    eax, eax
0x140060c89  jle     short loc_140060C94
0x140060c8b  movzx   ebx, ax
0x140060c8e  or      ebx, 80070000h
0x140060c94  test    rdi, rdi
0x140060c97  jz      short loc_140060CE6
0x140060c99  cmp     dword ptr [rbp+50h+var_A8], r14d
0x140060c9d  jz      short loc_140060CE6
0x140060c9f  mov     edx, [rbp+50h+var_98]
0x140060ca2  lea     r8, [rsp+150h+var_130]
0x140060ca7  xor     eax, eax
0x140060ca9  xorps   xmm0, xmm0
0x140060cac  mov     [rsp+150h+var_100], rax
0x140060cb1  mov     rcx, rdi
0x140060cb4  mov     eax, dword ptr [rbp+50h+var_A8+4]
0x140060cb7  mov     dword ptr [rsp+150h+var_100], eax
0x140060cbb  mov     eax, dword ptr [rbp+50h+var_A0]
0x140060cbe  movups  [rsp+150h+var_130], xmm0
0x140060cc3  mov     dword ptr [rsp+150h+var_100+4], eax
0x140060cc7  movups  [rsp+150h+var_120], xmm0
0x140060ccc  mov     qword ptr [rsp+150h+var_130+8], rsi
0x140060cd1  movups  [rsp+150h+var_110], xmm0
0x140060cd6  call    UnattendAddResults
0x140060cdb  cmp     [rdi], r14d
0x140060cde  jge     short loc_140060CE6
0x140060ce0  test    ebx, ebx
0x140060ce2  cmovs   ebx, r12d
0x140060ce6  mov     [rbp+50h+var_B0], r15
0x140060cea  cmp     [rbp+50h+P], r14
0x140060cee  jz      short loc_140060D2E
0x140060cf0  mov     rcx, gs:60h
0x140060cf9  xor     edx, edx; Flags
0x140060cfb  mov     r8, [rbp+50h+P]; P
0x140060cff  mov     rcx, [rcx+30h]; HeapHandle
0x140060d03  call    cs:__imp_RtlFreeHeap
0x140060d0a  nop     dword ptr [rax+rax+00h]
0x140060d0f  jmp     short loc_140060D2E
0x140060d11  mov     ecx, eax; Status
0x140060d13  call    cs:__imp_RtlNtStatusToDosError
0x140060d1a  nop     dword ptr [rax+rax+00h]
0x140060d1f  mov     ebx, eax
0x140060d21  test    eax, eax
0x140060d23  jle     short loc_140060D2E
0x140060d25  movzx   ebx, ax
0x140060d28  or      ebx, 80070000h
0x140060d2e  mov     rcx, gs:60h
0x140060d37  xor     edx, edx; Flags
0x140060d39  mov     r8, [rsp+150h+var_F8+8]; P
0x140060d3e  mov     rcx, [rcx+30h]; HeapHandle
0x140060d42  call    cs:__imp_RtlFreeHeap
0x140060d49  nop     dword ptr [rax+rax+00h]
0x140060d4e  lea     rcx, [rbp+50h+var_80]; this
0x140060d52  call    ??1CFileRtlFOStream@@QEAA@XZ; CFileRtlFOStream::~CFileRtlFOStream(void)
0x140060d57  jmp     short loc_140060D76
0x140060d59  mov     ecx, eax; Status
0x140060d5b  call    cs:__imp_RtlNtStatusToDosError
0x140060d62  nop     dword ptr [rax+rax+00h]
0x140060d67  mov     ebx, eax
0x140060d69  test    eax, eax
0x140060d6b  jle     short loc_140060D76
0x140060d6d  movzx   ebx, ax
0x140060d70  or      ebx, 80070000h
0x140060d76  mov     eax, ebx
0x140060d78  mov     rcx, [rbp+50h+var_40]
0x140060d7c  xor     rcx, rsp; StackCookie
0x140060d7f  call    __security_check_cookie
0x140060d84  add     rsp, 120h
0x140060d8b  pop     r15
0x140060d8d  pop     r14
0x140060d8f  pop     r12
0x140060d91  pop     rdi
0x140060d92  pop     rsi
0x140060d93  pop     rbx
0x140060d94  pop     rbp
0x140060d95  retn
```
