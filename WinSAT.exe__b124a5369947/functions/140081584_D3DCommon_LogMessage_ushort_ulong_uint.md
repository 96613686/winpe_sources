# D3DCommon::LogMessage(ushort,ulong,uint *)

- ea: `0x140081584`
- end: `0x1400816ba`
- name: `?LogMessage@D3DCommon@@YAJGKPEAI@Z`
- size: `310`
- prototype: `__int64 __fastcall(D3DCommon *__hidden this, unsigned __int16, unsigned int, unsigned int *)`
- caller_count: `9`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14007dbd0`
- `0x14007df08`
- `0x14007e67c`
- `0x14007ecbc`
- `0x14007fef4`
- `0x14008064c`
- `0x140080a04`
- `0x1400852f0`
- `0x140086a74`

## callees

- `0x140081584`
- `0x140113220`
- `0x14011a010`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x14008167e`
- `KERNEL32!DeviceIoControl` at `0x14008167e`
- `KERNEL32!CreateFileW` at `0x140081642`
- `KERNEL32!CreateFileW` at `0x140081642`
- `KERNEL32!GetLastError` at `0x140081688`
- `KERNEL32!GetLastError` at `0x140081688`

## pseudocode

```c
__int64 __fastcall D3DCommon::LogMessage(D3DCommon *this, int a2, int *a3, unsigned int *a4)
{
  __int16 v4; // ax
  HANDLE v5; // rcx
  unsigned int v7; // ebx
  int v8; // edi
  signed int LastError; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-38h] BYREF
  __int64 InBuffer; // [rsp+48h] [rbp-30h] BYREF
  int InBuffer_8; // [rsp+50h] [rbp-28h]
  int InBuffer_12; // [rsp+54h] [rbp-24h]
  int v14; // [rsp+58h] [rbp-20h]

  v4 = (__int16)this;
  BytesReturned = 0;
  v5 = qword_1401CBAA8;
  if ( !qword_1401CBAA8 )
    return 0;
  v7 = 0;
  v14 = 0;
  InBuffer = 0;
  WORD2(InBuffer) = v4;
  InBuffer_8 = -231621936;
  InBuffer_12 = a2;
  if ( a3 )
    v14 = *a3;
  v8 = a3 != 0 ? 4 : 0;
  if ( qword_1401CBA98 )
  {
    qword_1401CBA98(TraceHandle, &InBuffer, (unsigned int)(v8 + 16));
  }
  else if ( qword_1401CBAA8 == (HANDLE)-1LL
         && (qword_1401CBAA8 = CreateFileW(L"\\\\.\\WMIDataDevice", 0xC0000000, 0, 0, 3u, 0x80u, 0),
             v5 = qword_1401CBAA8,
             qword_1401CBAA8 == (HANDLE)-1LL)
         || !DeviceIoControl(v5, 0x2200A4u, &InBuffer, v8 + 16, 0, 0, &BytesReturned, 0) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v7;
}

```

## disassembly

```asm
0x140081584  mov     [rsp+arg_0], rbx
0x140081589  push    rdi
0x14008158a  sub     rsp, 70h
0x14008158e  mov     rax, cs:__security_cookie
0x140081595  xor     rax, rsp
0x140081598  mov     [rsp+78h+var_18], rax
0x14008159d  movzx   eax, cx
0x1400815a0  mov     [rsp+78h+BytesReturned], 0
0x1400815a8  mov     rcx, cs:qword_1401CBAA8
0x1400815af  test    rcx, rcx
0x1400815b2  jnz     short loc_1400815BB
0x1400815b4  xor     eax, eax
0x1400815b6  jmp     loc_14008169F
0x1400815bb  xor     r9d, r9d; lpSecurityAttributes
0x1400815be  xor     ebx, ebx
0x1400815c0  mov     [rsp+78h+var_20], r9d
0x1400815c5  xorps   xmm0, xmm0
0x1400815c8  movups  [rsp+78h+InBuffer], xmm0
0x1400815cd  mov     word ptr [rsp+78h+InBuffer+4], ax
0x1400815d2  mov     dword ptr [rsp+78h+InBuffer+8], 0F231BAD0h
0x1400815da  mov     dword ptr [rsp+78h+InBuffer+0Ch], edx
0x1400815de  test    r8, r8
0x1400815e1  jz      short loc_1400815EA
0x1400815e3  mov     eax, [r8]
0x1400815e6  mov     [rsp+78h+var_20], eax
0x1400815ea  mov     rax, cs:qword_1401CBA98
0x1400815f1  neg     r8
0x1400815f4  sbb     edi, edi
0x1400815f6  and     edi, 4
0x1400815f9  test    rax, rax
0x1400815fc  jz      short loc_140081618
0x1400815fe  mov     rcx, cs:TraceHandle
0x140081605  lea     r8d, [rdi+10h]
0x140081609  lea     rdx, [rsp+78h+InBuffer]
0x14008160e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140081613  jmp     loc_14008169D
0x140081618  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14008161c  jnz     short loc_140081658
0x14008161e  mov     [rsp+78h+hTemplateFile], rbx; hTemplateFile
0x140081623  lea     rcx, aWmidatadevice; "\\\\.\\WMIDataDevice"
0x14008162a  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140081632  xor     r8d, r8d; dwShareMode
0x140081635  mov     edx, 0C0000000h; dwDesiredAccess
0x14008163a  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x140081642  call    cs:__imp_CreateFileW
0x140081648  mov     cs:qword_1401CBAA8, rax
0x14008164f  mov     rcx, rax; hDevice
0x140081652  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140081656  jz      short loc_140081688
0x140081658  mov     [rsp+78h+lpOverlapped], rbx; lpOverlapped
0x14008165d  lea     rax, [rsp+78h+BytesReturned]
0x140081662  mov     [rsp+78h+hTemplateFile], rax; lpBytesReturned
0x140081667  lea     r9d, [rdi+10h]; nInBufferSize
0x14008166b  mov     [rsp+78h+dwFlagsAndAttributes], ebx; nOutBufferSize
0x14008166f  lea     r8, [rsp+78h+InBuffer]; lpInBuffer
0x140081674  mov     edx, 2200A4h; dwIoControlCode
0x140081679  mov     qword ptr [rsp+78h+dwCreationDisposition], rbx; lpOutBuffer
0x14008167e  call    cs:__imp_DeviceIoControl
0x140081684  test    eax, eax
0x140081686  jnz     short loc_14008169D
0x140081688  call    cs:__imp_GetLastError
0x14008168e  mov     ebx, eax
0x140081690  test    eax, eax
0x140081692  jle     short loc_14008169D
0x140081694  movzx   ebx, ax
0x140081697  or      ebx, 80070000h
0x14008169d  mov     eax, ebx
0x14008169f  mov     rcx, [rsp+78h+var_18]
0x1400816a4  xor     rcx, rsp; StackCookie
0x1400816a7  call    __security_check_cookie
0x1400816ac  mov     rbx, [rsp+78h+arg_0]
0x1400816b4  add     rsp, 70h
0x1400816b8  pop     rdi
0x1400816b9  retn
```
