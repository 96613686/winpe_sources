# CommonUtil::HrGetFileAttributes(ulong *,ushort const *)

- ea: `0x14000d6f8`
- end: `0x14000d770`
- name: `?HrGetFileAttributes@CommonUtil@@YAJPEAKPEBG@Z`
- size: `120`
- prototype: `__int64 __fastcall(CommonUtil *this, const WCHAR *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000d9e8`

## callees

- `0x14000d6f8`
- `0x14000dba8`
- `0x14000f7c8`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x14000d70b`
- `KERNEL32!GetFileAttributesW` at `0x14000d70b`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrGetFileAttributes(CommonUtil *this, const WCHAR *a2, const unsigned __int16 *a3)
{
  int v4; // edi
  DWORD FileAttributesW; // eax
  unsigned int LastFailure; // ebx

  v4 = (int)a2;
  FileAttributesW = GetFileAttributesW(a2);
  if ( FileAttributesW == -1 )
  {
    LastFailure = HrGetLastFailure();
    if ( LastFailure + 2147024894 > 1
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        (unsigned int)WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids,
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
0x14000d6f8  mov     [rsp+arg_0], rbx
0x14000d6fd  push    rdi
0x14000d6fe  sub     rsp, 30h
0x14000d702  mov     rbx, rcx
0x14000d705  mov     rdi, rdx
0x14000d708  mov     rcx, rdx; lpFileName
0x14000d70b  call    cs:__imp_GetFileAttributesW
0x14000d711  cmp     eax, 0FFFFFFFFh
0x14000d714  jnz     short loc_14000D761
0x14000d716  call    HrGetLastFailure
0x14000d71b  mov     ebx, eax
0x14000d71d  lea     ecx, [rax+7FF8FFFEh]
0x14000d723  cmp     ecx, 1
0x14000d726  jbe     short loc_14000D75D
0x14000d728  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d72f  lea     rax, WPP_GLOBAL_Control
0x14000d736  cmp     rcx, rax
0x14000d739  jz      short loc_14000D75D
0x14000d73b  test    byte ptr [rcx+1Ch], 1
0x14000d73f  jz      short loc_14000D75D
0x14000d741  mov     rcx, [rcx+10h]
0x14000d745  lea     r8, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids
0x14000d74c  mov     edx, 3Fh ; '?'
0x14000d751  mov     [rsp+38h+var_18], ebx
0x14000d755  mov     r9, rdi
0x14000d758  call    WPP_SF_Sd
0x14000d75d  mov     eax, ebx
0x14000d75f  jmp     short loc_14000D765
0x14000d761  mov     [rbx], eax
0x14000d763  xor     eax, eax
0x14000d765  mov     rbx, [rsp+38h+arg_0]
0x14000d76a  add     rsp, 30h
0x14000d76e  pop     rdi
0x14000d76f  retn
```
