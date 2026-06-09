# CbsOfflineUtil::CreateTemporyFolderForShimBinary(void)

- ea: `0x180042608`
- end: `0x18004277b`
- name: `?CreateTemporyFolderForShimBinary@CbsOfflineUtil@@AEAAJXZ`
- size: `371`
- prototype: `__int64 __fastcall(CbsOfflineUtil *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180042070`

## callees

- `0x18001aac4`
- `0x18001d460`
- `0x180020c30`
- `0x18002d2b0`
- `0x180042608`
- `0x180097e20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180042707`
- `KERNEL32!GetLastError` at `0x180042707`
- `KERNEL32!CreateDirectoryW` at `0x1800426f7`
- `KERNEL32!CreateDirectoryW` at `0x1800426f7`
- `ntdll!RtlRaiseStatus` at `0x180042742`
- `ntdll!RtlRaiseStatus` at `0x180042742`
- `OLE32!StringFromGUID2` at `0x1800426a8`
- `OLE32!StringFromGUID2` at `0x1800426a8`
- `OLE32!CoCreateGuid` at `0x180042682`
- `OLE32!CoCreateGuid` at `0x180042682`

## pseudocode

```c
__int64 __fastcall CbsOfflineUtil::CreateTemporyFolderForShimBinary(CbsOfflineUtil *this)
{
  int TemporaryPath; // ebx
  LPCWSTR v3; // rsi
  signed int LastError; // eax
  bool v5; // zf
  LPCWSTR lpPathName; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v8[3]; // [rsp+28h] [rbp-D8h] BYREF
  GUID pguid; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF

  memset(Buffer, 0, 0x208u);
  pguid = 0;
  memset(sz, 0, sizeof(sz));
  lpPathName = 0;
  TemporaryPath = GetTemporaryPath(0x104u, Buffer);
  if ( TemporaryPath >= 0 )
  {
    TemporaryPath = CoCreateGuid(&pguid);
    if ( TemporaryPath >= 0 )
    {
      StringFromGUID2(&pguid, sz, 40);
      v8[0] = L"\\\\?\\";
      v8[1] = Buffer;
      v8[2] = sz;
      TemporaryPath = ConcatManyStrings(3, v8, &lpPathName);
      if ( TemporaryPath >= 0 )
      {
        v3 = lpPathName;
        if ( CreateDirectoryW(lpPathName, 0) )
        {
          Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close((char *)this + 16);
          v5 = *((_QWORD *)this + 2) == 0;
          lpPathName = 0;
          if ( !v5 )
            RtlRaiseStatus(-1073741595);
          *((_QWORD *)this + 2) = v3;
        }
        else
        {
          LastError = GetLastError();
          TemporaryPath = LastError;
          if ( LastError > 0 )
            TemporaryPath = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&lpPathName);
  return (unsigned int)TemporaryPath;
}

```

## disassembly

```asm
0x180042608  push    rbp
0x18004260a  push    rbx
0x18004260b  push    rsi
0x18004260c  push    rdi
0x18004260d  lea     rbp, [rsp-1C8h]
0x180042615  sub     rsp, 2C8h
0x18004261c  mov     rax, cs:__security_cookie
0x180042623  xor     rax, rsp
0x180042626  mov     [rbp+1E0h+var_30], rax
0x18004262d  mov     rdi, rcx
0x180042630  xor     edx, edx; Val
0x180042632  lea     rcx, [rbp+1E0h+Buffer]; void *
0x180042636  mov     r8d, 208h; Size
0x18004263c  call    memset
0x180042641  xor     edx, edx; Val
0x180042643  lea     rcx, [rsp+2E0h+sz]; void *
0x180042648  xorps   xmm0, xmm0
0x18004264b  movups  xmmword ptr [rsp+2E0h+pguid.Data1], xmm0
0x180042650  lea     r8d, [rdx+50h]; Size
0x180042654  call    memset
0x180042659  xor     r8d, r8d
0x18004265c  mov     [rsp+2E0h+lpPathName], 0
0x180042665  lea     rdx, [rbp+1E0h+Buffer]; lpBuffer
0x180042669  mov     ecx, 104h; nBufferLength
0x18004266e  call    GetTemporaryPath
0x180042673  mov     ebx, eax
0x180042675  test    eax, eax
0x180042677  js      loc_180042753
0x18004267d  lea     rcx, [rsp+2E0h+pguid]; pguid
0x180042682  call    cs:__imp_CoCreateGuid
0x180042689  nop     dword ptr [rax+rax+00h]
0x18004268e  mov     ebx, eax
0x180042690  test    eax, eax
0x180042692  js      loc_180042753
0x180042698  mov     r8d, 28h ; '('; cchMax
0x18004269e  lea     rdx, [rsp+2E0h+sz]; lpsz
0x1800426a3  lea     rcx, [rsp+2E0h+pguid]; rguid
0x1800426a8  call    cs:__imp_StringFromGUID2
0x1800426af  nop     dword ptr [rax+rax+00h]
0x1800426b4  lea     rax, String1; "\\\\?\\"
0x1800426bb  mov     ecx, 3
0x1800426c0  mov     [rsp+2E0h+var_2B8], rax
0x1800426c5  lea     r8, [rsp+2E0h+lpPathName]
0x1800426ca  lea     rax, [rbp+1E0h+Buffer]
0x1800426ce  mov     [rsp+2E0h+var_2B0], rax
0x1800426d3  lea     rdx, [rsp+2E0h+var_2B8]
0x1800426d8  lea     rax, [rsp+2E0h+sz]
0x1800426dd  mov     [rsp+2E0h+var_2A8], rax
0x1800426e2  call    ConcatManyStrings
0x1800426e7  mov     ebx, eax
0x1800426e9  test    eax, eax
0x1800426eb  js      short loc_180042753
0x1800426ed  mov     rsi, [rsp+2E0h+lpPathName]
0x1800426f2  xor     edx, edx; lpSecurityAttributes
0x1800426f4  mov     rcx, rsi; lpPathName
0x1800426f7  call    cs:__imp_CreateDirectoryW
0x1800426fe  nop     dword ptr [rax+rax+00h]
0x180042703  test    eax, eax
0x180042705  jnz     short loc_180042724
0x180042707  call    cs:__imp_GetLastError
0x18004270e  nop     dword ptr [rax+rax+00h]
0x180042713  mov     ebx, eax
0x180042715  test    eax, eax
0x180042717  jle     short loc_180042753
0x180042719  movzx   ebx, ax
0x18004271c  or      ebx, 80070000h
0x180042722  jmp     short loc_180042753
0x180042724  lea     rcx, [rdi+10h]
0x180042728  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x18004272d  cmp     qword ptr [rdi+10h], 0
0x180042732  mov     [rsp+2E0h+lpPathName], 0
0x18004273b  jz      short loc_18004274F
0x18004273d  mov     ecx, 0C00000E5h; Status
0x180042742  call    cs:__imp_RtlRaiseStatus
0x180042749  nop     dword ptr [rax+rax+00h]
0x18004274e  int     3; Trap to Debugger
0x18004274f  mov     [rdi+10h], rsi
0x180042753  lea     rcx, [rsp+2E0h+lpPathName]
0x180042758  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x18004275d  mov     eax, ebx
0x18004275f  mov     rcx, [rbp+1E0h+var_30]
0x180042766  xor     rcx, rsp; StackCookie
0x180042769  call    __security_check_cookie
0x18004276e  add     rsp, 2C8h
0x180042775  pop     rdi
0x180042776  pop     rsi
0x180042777  pop     rbx
0x180042778  pop     rbp
0x180042779  retn
```
