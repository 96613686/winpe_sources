# GetDiffAreaInfo(ushort const *,__int64 *,__int64 *,__int64 *)

- ea: `0x1400066e0`
- end: `0x1400068cb`
- name: `?GetDiffAreaInfo@@YAJPEBGPEA_J11@Z`
- size: `491`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64 *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x140001dec`

## callees

- `0x140002e1c`
- `0x1400066e0`
- `0x140006cc8`
- `0x14000e324`
- `0x14000e41c`
- `0x14000fe8c`
- `0x1400103c4`
- `0x140010744`
- `0x140010980`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000689e`
- `KERNEL32!CloseHandle` at `0x14000689e`
- `KERNEL32!CreateFileW` at `0x1400067dd`
- `KERNEL32!CreateFileW` at `0x1400067dd`
- `KERNEL32!DeviceIoControl` at `0x140006843`
- `KERNEL32!DeviceIoControl` at `0x140006843`

## pseudocode

```c
__int64 __fastcall GetDiffAreaInfo(const unsigned __int16 *a1, __int64 *a2, __int64 *a3, __int64 *a4)
{
  unsigned __int16 v8; // dx
  int LastFailureAsHRESULT; // edi
  __int16 v10; // ax
  char *FileW; // rbx
  DWORD BytesReturned; // [rsp+40h] [rbp-49h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+48h] [rbp-41h] BYREF
  int v15; // [rsp+58h] [rbp-31h] BYREF
  __int16 v16; // [rsp+5Ch] [rbp-2Dh]
  __int16 v17; // [rsp+5Eh] [rbp-2Bh]
  __int128 OutBuffer; // [rsp+90h] [rbp+7h] BYREF
  __int64 v19; // [rsp+A0h] [rbp+17h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_5db9067f32c63af338ecd18e5c6d1769_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v15, "GetDiffAreaInfo", 210, 1);
  BytesReturned = 0;
  v19 = 0;
  lpFileName[1] = 0;
  lpFileName[0] = (LPCWSTR)qword_140013960;
  OutBuffer = 0;
  LastFailureAsHRESULT = CBsString::Append((CBsString *)lpFileName, a1);
  v15 = LastFailureAsHRESULT;
  v10 = 216;
  if ( LastFailureAsHRESULT < 0 )
  {
    FileW = 0;
LABEL_6:
    v17 = v10;
    goto LABEL_12;
  }
  v16 = 216;
  CBsString::UnTrailing((CBsString *)lpFileName, v8);
  FileW = (char *)CreateFileW(lpFileName[0], 0x80000000, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v15 = LastFailureAsHRESULT;
    v10 = 223;
    goto LABEL_6;
  }
  v16 = 223;
  v15 = 0;
  if ( !DeviceIoControl(FileW, 0x53002Cu, 0, 0, &OutBuffer, 0x18u, &BytesReturned, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v15 = LastFailureAsHRESULT;
    v10 = 232;
    goto LABEL_6;
  }
  v15 = 0;
  v16 = 232;
  LastFailureAsHRESULT = 0;
  *a2 = OutBuffer;
  *a3 = *((_QWORD *)&OutBuffer + 1);
  *a4 = v19;
LABEL_12:
  CBsString::_Release((LPVOID *)lpFileName);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v15);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x1400066e0  push    rbp
0x1400066e2  push    rbx
0x1400066e3  push    rsi
0x1400066e4  push    rdi
0x1400066e5  push    r14
0x1400066e7  push    r15
0x1400066e9  lea     rbp, [rsp-2Fh]
0x1400066ee  sub     rsp, 0B8h
0x1400066f5  mov     rax, cs:__security_cookie
0x1400066fc  xor     rax, rsp
0x1400066ff  mov     [rbp+57h+var_38], rax
0x140006703  mov     r15, r9
0x140006706  mov     r14, r8
0x140006709  mov     rsi, rdx
0x14000670c  mov     rbx, rcx
0x14000670f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006716  lea     rax, WPP_GLOBAL_Control
0x14000671d  cmp     rcx, rax
0x140006720  jz      short loc_140006740
0x140006722  test    dword ptr [rcx+1Ch], 20000000h
0x140006729  jz      short loc_140006740
0x14000672b  mov     rcx, [rcx+10h]
0x14000672f  lea     r8, WPP_5db9067f32c63af338ecd18e5c6d1769_Traceguids
0x140006736  mov     edx, 11h
0x14000673b  call    WPP_SF_
0x140006740  mov     r9d, 1; unsigned __int16
0x140006746  lea     rdx, aGetdiffareainf; "GetDiffAreaInfo"
0x14000674d  mov     r8d, 0D2h; unsigned __int16
0x140006753  lea     rcx, [rbp+57h+var_88]; this
0x140006757  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x14000675c  xor     eax, eax
0x14000675e  mov     [rbp+57h+BytesReturned], 0
0x140006765  mov     [rbp+57h+var_40], rax
0x140006769  xorps   xmm0, xmm0
0x14000676c  lea     rax, qword_140013960
0x140006773  mov     [rbp+57h+var_90], 0
0x14000677b  mov     [rbp+57h+lpFileName], rax
0x14000677f  movups  [rbp+57h+OutBuffer], xmm0
0x140006783  mov     rdx, rbx; unsigned __int16 *
0x140006786  lea     rcx, [rbp+57h+lpFileName]; this
0x14000678a  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x14000678f  mov     edi, eax
0x140006791  mov     [rbp+57h+var_88], eax
0x140006794  test    eax, eax
0x140006796  mov     eax, 0D8h
0x14000679b  jns     short loc_1400067A8
0x14000679d  xor     ebx, ebx
0x14000679f  mov     [rbp+57h+var_82], ax
0x1400067a3  jmp     loc_140006888
0x1400067a8  lea     rcx, [rbp+57h+lpFileName]; this
0x1400067ac  mov     [rbp+57h+var_84], ax
0x1400067b0  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x1400067b5  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1400067b9  mov     r8d, 3; dwShareMode
0x1400067bf  mov     [rsp+0E0h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x1400067c8  xor     r9d, r9d; lpSecurityAttributes
0x1400067cb  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400067d3  mov     edx, 80000000h; dwDesiredAccess
0x1400067d8  mov     [rsp+0E0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1400067dd  call    cs:__imp_CreateFileW
0x1400067e3  mov     rbx, rax
0x1400067e6  inc     rax
0x1400067e9  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400067ef  jnz     short loc_140006802
0x1400067f1  call    GetLastFailureAsHRESULT
0x1400067f6  mov     edi, eax
0x1400067f8  mov     [rbp+57h+var_88], eax
0x1400067fb  mov     eax, 0DFh
0x140006800  jmp     short loc_14000679F
0x140006802  mov     [rsp+0E0h+lpOverlapped], 0; lpOverlapped
0x14000680b  mov     eax, 0DFh
0x140006810  mov     [rbp+57h+var_84], ax
0x140006814  xor     r9d, r9d; nInBufferSize
0x140006817  lea     rax, [rbp+57h+BytesReturned]
0x14000681b  mov     [rbp+57h+var_88], 0
0x140006822  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x140006827  xor     r8d, r8d; lpInBuffer
0x14000682a  lea     rax, [rbp+57h+OutBuffer]
0x14000682e  mov     [rsp+0E0h+dwFlagsAndAttributes], 18h; nOutBufferSize
0x140006836  mov     edx, 53002Ch; dwIoControlCode
0x14000683b  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; lpOutBuffer
0x140006840  mov     rcx, rbx; hDevice
0x140006843  call    cs:__imp_DeviceIoControl
0x140006849  test    eax, eax
0x14000684b  jnz     short loc_140006861
0x14000684d  call    GetLastFailureAsHRESULT
0x140006852  mov     edi, eax
0x140006854  mov     [rbp+57h+var_88], eax
0x140006857  mov     eax, 0E8h
0x14000685c  jmp     loc_14000679F
0x140006861  mov     eax, 0E8h
0x140006866  mov     [rbp+57h+var_88], 0
0x14000686d  mov     [rbp+57h+var_84], ax
0x140006871  xor     edi, edi
0x140006873  mov     rax, qword ptr [rbp+57h+OutBuffer]
0x140006877  mov     [rsi], rax
0x14000687a  mov     rax, qword ptr [rbp+57h+OutBuffer+8]
0x14000687e  mov     [r14], rax
0x140006881  mov     rax, [rbp+57h+var_40]
0x140006885  mov     [r15], rax
0x140006888  lea     rcx, [rbp+57h+lpFileName]; this
0x14000688c  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x140006891  lea     rcx, [rbx-1]
0x140006895  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140006899  ja      short loc_1400068A4
0x14000689b  mov     rcx, rbx; hObject
0x14000689e  call    cs:__imp_CloseHandle
0x1400068a4  lea     rcx, [rbp+57h+var_88]; this
0x1400068a8  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1400068ad  mov     eax, edi
0x1400068af  mov     rcx, [rbp+57h+var_38]
0x1400068b3  xor     rcx, rsp; StackCookie
0x1400068b6  call    __security_check_cookie
0x1400068bb  add     rsp, 0B8h
0x1400068c2  pop     r15
0x1400068c4  pop     r14
0x1400068c6  pop     rdi
0x1400068c7  pop     rsi
0x1400068c8  pop     rbx
0x1400068c9  pop     rbp
0x1400068ca  retn
```
