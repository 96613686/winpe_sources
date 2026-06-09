# AssessmentCore::IsEndOfSupport(int &)

- ea: `0x180009b00`
- end: `0x180009b50`
- name: `?IsEndOfSupport@AssessmentCore@@MEAAJAEAH@Z`
- size: `80`
- prototype: `__int64 __fastcall(AssessmentCore *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009b00`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009b24`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009b24`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180009b33`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180009b33`

## pseudocode

```c
__int64 __fastcall AssessmentCore::IsEndOfSupport(AssessmentCore *this, int *a2)
{
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp+8h] BYREF

  SystemTimeAsFileTime = 0;
  *a2 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( CompareFileTime(&SystemTimeAsFileTime, (const FILETIME *)((char *)this + 116)) >= 0 )
    *a2 = 1;
  return 0;
}

```

## disassembly

```asm
0x180009b00  mov     [rsp+arg_8], rbx
0x180009b05  push    rdi
0x180009b06  sub     rsp, 20h
0x180009b0a  mov     rbx, rcx
0x180009b0d  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180009b16  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180009b1b  mov     dword ptr [rdx], 0
0x180009b21  mov     rdi, rdx
0x180009b24  call    cs:__imp_GetSystemTimeAsFileTime
0x180009b2a  lea     rdx, [rbx+74h]; lpFileTime2
0x180009b2e  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpFileTime1
0x180009b33  call    cs:__imp_CompareFileTime
0x180009b39  test    eax, eax
0x180009b3b  js      short loc_180009B43
0x180009b3d  mov     dword ptr [rdi], 1
0x180009b43  mov     rbx, [rsp+28h+arg_8]
0x180009b48  xor     eax, eax
0x180009b4a  add     rsp, 20h
0x180009b4e  pop     rdi
0x180009b4f  retn
```
