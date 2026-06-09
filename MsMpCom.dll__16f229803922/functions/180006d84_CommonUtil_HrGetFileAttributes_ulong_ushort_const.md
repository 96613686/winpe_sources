# CommonUtil::HrGetFileAttributes(ulong *,ushort const *)

- ea: `0x180006d84`
- end: `0x180006dfc`
- name: `?HrGetFileAttributes@CommonUtil@@YAJPEAKPEBG@Z`
- size: `120`
- prototype: `__int64 __fastcall(CommonUtil *this, const WCHAR *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007148`

## callees

- `0x180006898`
- `0x180006d84`
- `0x1800090e4`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180006d97`
- `KERNEL32!GetFileAttributesW` at `0x180006d97`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrGetFileAttributes(CommonUtil *this, const WCHAR *a2, const unsigned __int16 *a3)
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
        63,
        (unsigned int)&WPP_e2b92b5a14063cae8af40d4f75517e75_Traceguids,
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
0x180006d84  mov     [rsp+arg_0], rbx
0x180006d89  push    rdi
0x180006d8a  sub     rsp, 30h
0x180006d8e  mov     rbx, rcx
0x180006d91  mov     rdi, rdx
0x180006d94  mov     rcx, rdx; lpFileName
0x180006d97  call    cs:__imp_GetFileAttributesW
0x180006d9d  cmp     eax, 0FFFFFFFFh
0x180006da0  jnz     short loc_180006DED
0x180006da2  call    HrGetLastFailure
0x180006da7  mov     ebx, eax
0x180006da9  lea     ecx, [rax+7FF8FFFEh]
0x180006daf  cmp     ecx, 1
0x180006db2  jbe     short loc_180006DE9
0x180006db4  mov     rcx, cs:WPP_GLOBAL_Control
0x180006dbb  lea     rax, WPP_GLOBAL_Control
0x180006dc2  cmp     rcx, rax
0x180006dc5  jz      short loc_180006DE9
0x180006dc7  test    byte ptr [rcx+1Ch], 1
0x180006dcb  jz      short loc_180006DE9
0x180006dcd  mov     rcx, [rcx+10h]
0x180006dd1  lea     r8, WPP_e2b92b5a14063cae8af40d4f75517e75_Traceguids
0x180006dd8  mov     edx, 3Fh ; '?'
0x180006ddd  mov     [rsp+38h+var_18], ebx
0x180006de1  mov     r9, rdi
0x180006de4  call    WPP_SF_Sd
0x180006de9  mov     eax, ebx
0x180006deb  jmp     short loc_180006DF1
0x180006ded  mov     [rbx], eax
0x180006def  xor     eax, eax
0x180006df1  mov     rbx, [rsp+38h+arg_0]
0x180006df6  add     rsp, 30h
0x180006dfa  pop     rdi
0x180006dfb  retn
```
