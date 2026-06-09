# CommonUtil::UtilGetFileSize(unsigned __int64 *,void *)

- ea: `0x140004440`
- end: `0x1400044cf`
- name: `?UtilGetFileSize@CommonUtil@@YAJPEA_KPEAX@Z`
- size: `143`
- prototype: `int(CommonUtil *__hidden this, unsigned __int64 *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002380c`

## callees

- `0x140004440`
- `0x14000493c`
- `0x140005c20`
- `0x14001da70`

## import_xrefs

- `KERNEL32!GetFileSizeEx` at `0x14000446c`
- `KERNEL32!GetFileSizeEx` at `0x14000446c`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilGetFileSize(_LARGE_INTEGER *this, unsigned __int64 *a2, void *a3)
{
  unsigned int LastFailure; // ebx
  _LARGE_INTEGER FileSize; // [rsp+20h] [rbp-18h] BYREF

  FileSize.QuadPart = 0;
  if ( GetFileSizeEx(a2, &FileSize) )
  {
    *this = FileSize;
    return 0;
  }
  else
  {
    LastFailure = HrGetLastFailure();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_bed851edf8673fd54b380593fb017a56_Traceguids, LastFailure);
    return LastFailure;
  }
}

```

## disassembly

```asm
0x140004440  push    rbx
0x140004442  sub     rsp, 30h
0x140004446  mov     rax, cs:__security_cookie
0x14000444d  xor     rax, rsp
0x140004450  mov     [rsp+38h+var_10], rax
0x140004455  mov     rax, rdx
0x140004458  mov     qword ptr [rsp+38h+FileSize], 0
0x140004461  mov     rbx, rcx
0x140004464  lea     rdx, [rsp+38h+FileSize]; lpFileSize
0x140004469  mov     rcx, rax; hFile
0x14000446c  call    cs:__imp_GetFileSizeEx
0x140004472  test    eax, eax
0x140004474  jnz     short loc_1400044B2
0x140004476  call    HrGetLastFailure
0x14000447b  mov     ebx, eax
0x14000447d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004484  lea     rax, WPP_GLOBAL_Control
0x14000448b  cmp     rcx, rax
0x14000448e  jz      short loc_1400044AE
0x140004490  test    byte ptr [rcx+1Ch], 1
0x140004494  jz      short loc_1400044AE
0x140004496  mov     rcx, [rcx+10h]
0x14000449a  lea     r8, WPP_bed851edf8673fd54b380593fb017a56_Traceguids
0x1400044a1  mov     edx, 19h
0x1400044a6  mov     r9d, ebx
0x1400044a9  call    WPP_SF_d
0x1400044ae  mov     eax, ebx
0x1400044b0  jmp     short loc_1400044BC
0x1400044b2  mov     rax, qword ptr [rsp+38h+FileSize]
0x1400044b7  mov     [rbx], rax
0x1400044ba  xor     eax, eax
0x1400044bc  mov     rcx, [rsp+38h+var_10]
0x1400044c1  xor     rcx, rsp; StackCookie
0x1400044c4  call    __security_check_cookie
0x1400044c9  add     rsp, 30h
0x1400044cd  pop     rbx
0x1400044ce  retn
```
