# MpCopyFileApiToStr

- ea: `0x14001eee0`
- end: `0x14001ef92`
- name: `MpCopyFileApiToStr`
- size: `178`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14001f304`
- `0x14001f6a0`
- `0x14001fce0`

## callees

- `0x14001da70`
- `0x14001eee0`

## string_xrefs

- `0x14001ef77`: `CopyFileEx`
- `0x14001ef66`: `CopyFile2`
- `0x14001ef55`: `CopyFileExAsync`
- `0x14001ef44`: `CopyFile2Async`

## pseudocode

```c
const wchar_t **__fastcall MpCopyFileApiToStr(const wchar_t **a1, unsigned int a2)
{
  const wchar_t *v3; // rax

  if ( a2 )
  {
    switch ( a2 )
    {
      case 1u:
        v3 = L"CopyFile2";
        a1[1] = (const wchar_t *)9;
        break;
      case 2u:
        v3 = L"CopyFileExAsync";
        a1[1] = (const wchar_t *)15;
        break;
      case 3u:
        v3 = L"CopyFile2Async";
        a1[1] = (const wchar_t *)14;
        break;
      default:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids, a2);
        v3 = L"Unknown";
        a1[1] = (const wchar_t *)7;
        break;
    }
  }
  else
  {
    v3 = L"CopyFileEx";
    a1[1] = (const wchar_t *)10;
  }
  *a1 = v3;
  return a1;
}

```

## disassembly

```asm
0x14001eee0  push    rbx
0x14001eee2  sub     rsp, 20h
0x14001eee6  mov     rbx, rcx
0x14001eee9  mov     ecx, edx
0x14001eeeb  mov     r9d, edx
0x14001eeee  test    edx, edx
0x14001eef0  jz      loc_14001EF77
0x14001eef6  sub     ecx, 1
0x14001eef9  jz      short loc_14001EF66
0x14001eefb  sub     ecx, 1
0x14001eefe  jz      short loc_14001EF55
0x14001ef00  cmp     ecx, 1
0x14001ef03  jz      short loc_14001EF44
0x14001ef05  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ef0c  lea     rax, WPP_GLOBAL_Control
0x14001ef13  cmp     rcx, rax
0x14001ef16  jz      short loc_14001EF33
0x14001ef18  test    byte ptr [rcx+1Ch], 2
0x14001ef1c  jz      short loc_14001EF33
0x14001ef1e  mov     rcx, [rcx+10h]
0x14001ef22  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14001ef29  mov     edx, 1Eh
0x14001ef2e  call    WPP_SF_d
0x14001ef33  lea     rax, aUnknown; "Unknown"
0x14001ef3a  mov     qword ptr [rbx+8], 7
0x14001ef42  jmp     short loc_14001EF86
0x14001ef44  lea     rax, aCopyfile2async; "CopyFile2Async"
0x14001ef4b  mov     qword ptr [rbx+8], 0Eh
0x14001ef53  jmp     short loc_14001EF86
0x14001ef55  lea     rax, aCopyfileexasyn; "CopyFileExAsync"
0x14001ef5c  mov     qword ptr [rbx+8], 0Fh
0x14001ef64  jmp     short loc_14001EF86
0x14001ef66  lea     rax, aCopyfile2; "CopyFile2"
0x14001ef6d  mov     qword ptr [rbx+8], 9
0x14001ef75  jmp     short loc_14001EF86
0x14001ef77  lea     rax, aCopyfileex; "CopyFileEx"
0x14001ef7e  mov     qword ptr [rbx+8], 0Ah
0x14001ef86  mov     [rbx], rax
0x14001ef89  mov     rax, rbx
0x14001ef8c  add     rsp, 20h
0x14001ef90  pop     rbx
0x14001ef91  retn
```
