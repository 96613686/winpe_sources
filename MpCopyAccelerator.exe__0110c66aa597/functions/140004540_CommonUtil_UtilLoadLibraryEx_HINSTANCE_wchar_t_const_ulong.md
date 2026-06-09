# CommonUtil::UtilLoadLibraryEx(HINSTANCE__ * *,wchar_t const *,ulong)

- ea: `0x140004540`
- end: `0x1400045fc`
- name: `?UtilLoadLibraryEx@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEB_WK@Z`
- size: `188`
- prototype: `int(CommonUtil *__hidden this, HINSTANCE *, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003c50`

## callees

- `0x140004540`
- `0x14000493c`
- `0x140020220`
- `0x140023414`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x14000459a`
- `KERNEL32!LoadLibraryExW` at `0x14000459a`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilLoadLibraryEx(CommonUtil *this, HINSTANCE *a2, const wchar_t *a3)
{
  DWORD v3; // edi
  HMODULE Library; // rax
  unsigned int LastFailure; // eax
  unsigned int v8; // ebx

  v3 = (unsigned int)a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      (unsigned int)WPP_bed851edf8673fd54b380593fb017a56_Traceguids,
      (_DWORD)a2,
      (char)a3);
  Library = LoadLibraryExW((LPCWSTR)a2, 0, v3);
  *(_QWORD *)this = Library;
  if ( Library )
    return 0;
  LastFailure = HrGetLastFailure();
  v8 = LastFailure;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SDd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      (unsigned int)WPP_bed851edf8673fd54b380593fb017a56_Traceguids,
      (_DWORD)a2,
      v3,
      LastFailure);
  return v8;
}

```

## disassembly

```asm
0x140004540  mov     rax, rsp
0x140004543  mov     [rax+8], rbx
0x140004547  mov     [rax+10h], rbp
0x14000454b  mov     [rax+18h], rsi
0x14000454f  push    rdi
0x140004550  sub     rsp, 30h
0x140004554  mov     edi, r8d
0x140004557  mov     rsi, rdx
0x14000455a  mov     rbx, rcx
0x14000455d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004564  lea     rbp, WPP_GLOBAL_Control
0x14000456b  cmp     rcx, rbp
0x14000456e  jz      short loc_140004592
0x140004570  test    byte ptr [rcx+1Ch], 4
0x140004574  jz      short loc_140004592
0x140004576  mov     rcx, [rcx+10h]
0x14000457a  mov     edx, 1Eh
0x14000457f  mov     [rax-18h], r8d
0x140004583  mov     r9, rsi
0x140004586  lea     r8, WPP_bed851edf8673fd54b380593fb017a56_Traceguids
0x14000458d  call    WPP_SF_Sd
0x140004592  mov     r8d, edi; dwFlags
0x140004595  xor     edx, edx; hFile
0x140004597  mov     rcx, rsi; lpLibFileName
0x14000459a  call    cs:__imp_LoadLibraryExW
0x1400045a0  mov     [rbx], rax
0x1400045a3  test    rax, rax
0x1400045a6  jnz     short loc_1400045E5
0x1400045a8  call    HrGetLastFailure
0x1400045ad  mov     ebx, eax
0x1400045af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400045b6  cmp     rcx, rbp
0x1400045b9  jz      short loc_1400045E1
0x1400045bb  test    byte ptr [rcx+1Ch], 1
0x1400045bf  jz      short loc_1400045E1
0x1400045c1  mov     rcx, [rcx+10h]
0x1400045c5  lea     r8, WPP_bed851edf8673fd54b380593fb017a56_Traceguids
0x1400045cc  mov     [rsp+38h+var_10], eax
0x1400045d0  mov     edx, 1Fh
0x1400045d5  mov     r9, rsi
0x1400045d8  mov     [rsp+38h+var_18], edi
0x1400045dc  call    WPP_SF_SDd
0x1400045e1  mov     eax, ebx
0x1400045e3  jmp     short loc_1400045E7
0x1400045e5  xor     eax, eax
0x1400045e7  mov     rbx, [rsp+38h+arg_0]
0x1400045ec  mov     rbp, [rsp+38h+arg_8]
0x1400045f1  mov     rsi, [rsp+38h+arg_10]
0x1400045f6  add     rsp, 30h
0x1400045fa  pop     rdi
0x1400045fb  retn
```
