# CommonUtil::HrGetFileAttributes(ulong *,ushort const *)

- ea: `0x14000e780`
- end: `0x14000e7f8`
- name: `?HrGetFileAttributes@CommonUtil@@YAJPEAKPEBG@Z`
- size: `120`
- prototype: `__int64 __fastcall(CommonUtil *this, const WCHAR *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000e8b4`
- `0x14000ec0c`

## callees

- `0x1400071c0`
- `0x14000e780`
- `0x140011234`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x14000e793`
- `KERNEL32!GetFileAttributesW` at `0x14000e793`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrGetFileAttributes(CommonUtil *this, const WCHAR *a2, const unsigned __int16 *a3)
{
  int v4; // edi
  DWORD FileAttributesW; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int LastFailure; // ebx

  v4 = (int)a2;
  FileAttributesW = GetFileAttributesW(a2);
  if ( FileAttributesW == -1 )
  {
    LastFailure = HrGetLastFailure(v7, v6, v8, v9);
    if ( LastFailure + 2147024894 > 1
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        (unsigned int)&WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids,
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
0x14000e780  mov     [rsp+arg_0], rbx
0x14000e785  push    rdi
0x14000e786  sub     rsp, 30h
0x14000e78a  mov     rbx, rcx
0x14000e78d  mov     rdi, rdx
0x14000e790  mov     rcx, rdx; lpFileName
0x14000e793  call    cs:__imp_GetFileAttributesW
0x14000e799  cmp     eax, 0FFFFFFFFh
0x14000e79c  jnz     short loc_14000E7E9
0x14000e79e  call    HrGetLastFailure
0x14000e7a3  mov     ebx, eax
0x14000e7a5  lea     ecx, [rax+7FF8FFFEh]
0x14000e7ab  cmp     ecx, 1
0x14000e7ae  jbe     short loc_14000E7E5
0x14000e7b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e7b7  lea     rax, WPP_GLOBAL_Control
0x14000e7be  cmp     rcx, rax
0x14000e7c1  jz      short loc_14000E7E5
0x14000e7c3  test    byte ptr [rcx+1Ch], 1
0x14000e7c7  jz      short loc_14000E7E5
0x14000e7c9  mov     rcx, [rcx+10h]
0x14000e7cd  lea     r8, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids
0x14000e7d4  mov     edx, 3Fh ; '?'
0x14000e7d9  mov     [rsp+38h+var_18], ebx
0x14000e7dd  mov     r9, rdi
0x14000e7e0  call    WPP_SF_Sd
0x14000e7e5  mov     eax, ebx
0x14000e7e7  jmp     short loc_14000E7ED
0x14000e7e9  mov     [rbx], eax
0x14000e7eb  xor     eax, eax
0x14000e7ed  mov     rbx, [rsp+38h+arg_0]
0x14000e7f2  add     rsp, 30h
0x14000e7f6  pop     rdi
0x14000e7f7  retn
```
