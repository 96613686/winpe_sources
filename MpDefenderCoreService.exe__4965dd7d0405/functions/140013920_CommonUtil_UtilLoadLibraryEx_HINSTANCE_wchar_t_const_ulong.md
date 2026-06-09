# CommonUtil::UtilLoadLibraryEx(HINSTANCE__ * *,wchar_t const *,ulong)

- ea: `0x140013920`
- end: `0x1400139dc`
- name: `?UtilLoadLibraryEx@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEB_WK@Z`
- size: `188`
- prototype: `int(CommonUtil *__hidden this, HINSTANCE *, const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000b630`
- `0x14000dc50`

## callees

- `0x140013920`
- `0x140017738`
- `0x140085d94`
- `0x14008d178`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x14001397a`
- `KERNEL32!LoadLibraryExW` at `0x14001397a`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilLoadLibraryEx(CommonUtil *this, HINSTANCE *a2, const wchar_t *a3)
{
  DWORD v3; // edi
  HMODULE Library; // rax
  unsigned int LastFailure; // eax
  unsigned int v8; // ebx

  v3 = (unsigned int)a3;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_Sd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      30,
      (unsigned int)WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids,
      (_DWORD)a2,
      (char)a3);
  Library = LoadLibraryExW((LPCWSTR)a2, 0, v3);
  *(_QWORD *)this = Library;
  if ( Library )
    return 0;
  LastFailure = HrGetLastFailure();
  v8 = LastFailure;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_SLd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      31,
      (unsigned int)WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids,
      (_DWORD)a2,
      v3,
      LastFailure);
  return v8;
}

```

## disassembly

```asm
0x140013920  mov     rax, rsp
0x140013923  mov     [rax+8], rbx
0x140013927  mov     [rax+10h], rbp
0x14001392b  mov     [rax+18h], rsi
0x14001392f  push    rdi
0x140013930  sub     rsp, 30h
0x140013934  mov     edi, r8d
0x140013937  mov     rsi, rdx
0x14001393a  mov     rbx, rcx
0x14001393d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013944  lea     rbp, WPP_GLOBAL_Control
0x14001394b  cmp     rcx, rbp
0x14001394e  jz      short loc_140013972
0x140013950  test    byte ptr [rcx+1Ch], 4
0x140013954  jz      short loc_140013972
0x140013956  mov     rcx, [rcx+10h]
0x14001395a  mov     edx, 1Eh
0x14001395f  mov     [rax-18h], r8d
0x140013963  mov     r9, rsi
0x140013966  lea     r8, WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids
0x14001396d  call    WPP_SF_Sd
0x140013972  mov     r8d, edi; dwFlags
0x140013975  xor     edx, edx; hFile
0x140013977  mov     rcx, rsi; lpLibFileName
0x14001397a  call    cs:__imp_LoadLibraryExW
0x140013980  mov     [rbx], rax
0x140013983  test    rax, rax
0x140013986  jnz     short loc_1400139C5
0x140013988  call    HrGetLastFailure
0x14001398d  mov     ebx, eax
0x14001398f  mov     rcx, cs:WPP_GLOBAL_Control
0x140013996  cmp     rcx, rbp
0x140013999  jz      short loc_1400139C1
0x14001399b  test    byte ptr [rcx+1Ch], 1
0x14001399f  jz      short loc_1400139C1
0x1400139a1  mov     rcx, [rcx+10h]
0x1400139a5  lea     r8, WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids
0x1400139ac  mov     [rsp+38h+var_10], eax
0x1400139b0  mov     edx, 1Fh
0x1400139b5  mov     r9, rsi
0x1400139b8  mov     [rsp+38h+var_18], edi
0x1400139bc  call    WPP_SF_SLd
0x1400139c1  mov     eax, ebx
0x1400139c3  jmp     short loc_1400139C7
0x1400139c5  xor     eax, eax
0x1400139c7  mov     rbx, [rsp+38h+arg_0]
0x1400139cc  mov     rbp, [rsp+38h+arg_8]
0x1400139d1  mov     rsi, [rsp+38h+arg_10]
0x1400139d6  add     rsp, 30h
0x1400139da  pop     rdi
0x1400139db  retn
```
