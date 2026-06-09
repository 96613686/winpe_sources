# GetDaysBetweenFileTimes(_FILETIME,_FILETIME,ulong *)

- ea: `0x180018808`
- end: `0x180018880`
- name: `?GetDaysBetweenFileTimes@@YAJU_FILETIME@@0PEAK@Z`
- size: `120`
- prototype: `__int64 __fastcall(struct _FILETIME, struct _FILETIME, unsigned int *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007530`
- `0x180007900`
- `0x180009020`
- `0x1800186f0`

## callees

- `0x180018808`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018842`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018842`

## pseudocode

```c
__int64 __fastcall GetDaysBetweenFileTimes(FILETIME a1, FILETIME a2, unsigned int *a3)
{
  LONG v4; // edx
  unsigned __int64 v5; // rax
  FILETIME FileTime1; // [rsp+40h] [rbp+8h] BYREF
  FILETIME FileTime2; // [rsp+48h] [rbp+10h] BYREF
  FILETIME v10; // [rsp+58h] [rbp+20h]

  FileTime2 = a2;
  FileTime1 = a1;
  v10 = a2;
  v4 = CompareFileTime(&FileTime1, &FileTime2);
  v5 = *(_QWORD *)&a1 - *(_QWORD *)&v10;
  if ( v4 <= 0 )
    v5 = *(_QWORD *)&v10 - *(_QWORD *)&a1;
  if ( v5 )
    v5 /= 0xC92A69C000uLL;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180018808  mov     qword ptr [rsp+FileTime2.dwLowDateTime], rdx
0x18001880d  mov     qword ptr [rsp+FileTime1.dwLowDateTime], rcx
0x180018812  push    rbx
0x180018813  sub     rsp, 30h
0x180018817  mov     rax, rcx
0x18001881a  mov     dword ptr [rsp+38h+var_18], ecx
0x18001881e  shr     rax, 20h
0x180018822  lea     rcx, [rsp+38h+FileTime1]; lpFileTime1
0x180018827  mov     dword ptr [rsp+38h+var_18+4], eax
0x18001882b  mov     rbx, r8
0x18001882e  mov     rax, rdx
0x180018831  mov     dword ptr [rsp+38h+arg_18], edx
0x180018835  shr     rax, 20h
0x180018839  lea     rdx, [rsp+38h+FileTime2]; lpFileTime2
0x18001883e  mov     dword ptr [rsp+38h+arg_18+4], eax
0x180018842  call    cs:__imp_CompareFileTime
0x180018848  mov     rcx, [rsp+38h+arg_18]
0x18001884d  mov     edx, eax
0x18001884f  mov     rax, [rsp+38h+var_18]
0x180018854  sub     rcx, rax
0x180018857  sub     rax, [rsp+38h+arg_18]
0x18001885c  test    edx, edx
0x18001885e  cmovle  rax, rcx
0x180018862  test    rax, rax
0x180018865  jz      short loc_180018876
0x180018867  xor     edx, edx
0x180018869  mov     rcx, 0C92A69C000h
0x180018873  div     rcx
0x180018876  mov     [rbx], eax
0x180018878  xor     eax, eax
0x18001887a  add     rsp, 30h
0x18001887e  pop     rbx
0x18001887f  retn
```
