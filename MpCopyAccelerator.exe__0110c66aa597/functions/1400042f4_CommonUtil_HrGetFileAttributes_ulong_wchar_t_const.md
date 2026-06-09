# CommonUtil::HrGetFileAttributes(ulong *,wchar_t const *)

- ea: `0x1400042f4`
- end: `0x14000436c`
- name: `?HrGetFileAttributes@CommonUtil@@YAJPEAKPEB_W@Z`
- size: `120`
- prototype: `int(CommonUtil *__hidden this, unsigned int *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400044d0`

## callees

- `0x1400042f4`
- `0x14000493c`
- `0x140020220`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x140004307`
- `KERNEL32!GetFileAttributesW` at `0x140004307`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrGetFileAttributes(CommonUtil *this, const WCHAR *a2, const wchar_t *a3)
{
  int v4; // edi
  DWORD FileAttributesW; // eax
  __int64 v6; // rcx
  unsigned int LastFailure; // ebx

  v4 = (int)a2;
  FileAttributesW = GetFileAttributesW(a2);
  if ( FileAttributesW == -1 )
  {
    LastFailure = HrGetLastFailure(v6);
    if ( LastFailure + 2147024894 > 1
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        (unsigned int)WPP_bed851edf8673fd54b380593fb017a56_Traceguids,
        v4,
        LastFailure);
    }
    return LastFailure;
  }
  else
  {
    *(_DWORD *)this = FileAttributesW;
    return 0;
  }
}

```

## disassembly

```asm
0x1400042f4  mov     [rsp+arg_0], rbx
0x1400042f9  push    rdi
0x1400042fa  sub     rsp, 30h
0x1400042fe  mov     rbx, rcx
0x140004301  mov     rdi, rdx
0x140004304  mov     rcx, rdx; lpFileName
0x140004307  call    cs:__imp_GetFileAttributesW
0x14000430d  cmp     eax, 0FFFFFFFFh
0x140004310  jnz     short loc_14000435D
0x140004312  call    HrGetLastFailure
0x140004317  mov     ebx, eax
0x140004319  lea     ecx, [rax+7FF8FFFEh]
0x14000431f  cmp     ecx, 1
0x140004322  jbe     short loc_140004359
0x140004324  mov     rcx, cs:WPP_GLOBAL_Control
0x14000432b  lea     rax, WPP_GLOBAL_Control
0x140004332  cmp     rcx, rax
0x140004335  jz      short loc_140004359
0x140004337  test    byte ptr [rcx+1Ch], 1
0x14000433b  jz      short loc_140004359
0x14000433d  mov     rcx, [rcx+10h]
0x140004341  lea     r8, WPP_bed851edf8673fd54b380593fb017a56_Traceguids
0x140004348  mov     edx, 22h ; '"'
0x14000434d  mov     [rsp+38h+var_18], ebx
0x140004351  mov     r9, rdi
0x140004354  call    WPP_SF_Sd
0x140004359  mov     eax, ebx
0x14000435b  jmp     short loc_140004361
0x14000435d  mov     [rbx], eax
0x14000435f  xor     eax, eax
0x140004361  mov     rbx, [rsp+38h+arg_0]
0x140004366  add     rsp, 30h
0x14000436a  pop     rdi
0x14000436b  retn
```
