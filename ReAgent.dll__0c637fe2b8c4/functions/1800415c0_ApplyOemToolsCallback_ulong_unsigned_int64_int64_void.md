# ApplyOemToolsCallback(ulong,unsigned __int64,__int64,void *)

- ea: `0x1800415c0`
- end: `0x1800416ee`
- name: `?ApplyOemToolsCallback@@YAKK_K_JPEAX@Z`
- size: `302`
- prototype: `__int64 __fastcall(int, const wchar_t *, _DWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800059fc`
- `0x1800415c0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180041627`
- `msvcrt!_wcsnicmp` at `0x180041627`
- `KERNEL32!GetFileAttributesW` at `0x18004164c`
- `KERNEL32!GetFileAttributesW` at `0x18004164c`
- `KERNEL32!CompareStringW` at `0x1800416c5`
- `KERNEL32!CompareStringW` at `0x1800416c5`

## string_xrefs

- `0x18004163b`: `ApplyOemToolsCallback: Deciding whether to migrate OEM tool path [%s]`
- `0x180041666`: `ApplyOemToolsCallback: -> Target exists but is a directory, processing recursively`
- `0x18004167a`: `ApplyOemToolsCallback: -> Target file already exists uplevel, skipping`
- `0x1800416b9`: `winreconfig.xml`

## pseudocode

```c
__int64 __fastcall ApplyOemToolsCallback(int a1, const wchar_t *a2, _DWORD *a3, _DWORD *a4)
{
  unsigned int v7; // esi
  const wchar_t *v8; // rdx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rcx
  const wchar_t *v11; // r9
  size_t v12; // r8
  DWORD FileAttributesW; // eax
  unsigned __int64 v14; // rax

  if ( !a1 )
    return 87;
  v7 = 0;
  if ( a1 == 38009 )
  {
    v8 = *(const wchar_t **)a4;
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
    v11 = *(const wchar_t **)a4;
    v12 = -1;
    if ( v10 < v9 )
      v11 = a2;
    do
      ++v12;
    while ( v11[v12] );
    if ( _wcsnicmp(a2, v8, v12) )
    {
      *a3 = 0;
      return v7;
    }
    UnattendLogW(0, L"ApplyOemToolsCallback: Deciding whether to migrate OEM tool path [%s]", a2);
    FileAttributesW = GetFileAttributesW(a2);
    if ( FileAttributesW == -1 )
    {
      UnattendLogW(0, L"ApplyOemToolsCallback: -> Target does not exist in uplevel WIM, will process");
    }
    else
    {
      if ( (FileAttributesW & 0x10) == 0 )
      {
        UnattendLogW(0, L"ApplyOemToolsCallback: -> Target file already exists uplevel, skipping");
        *a3 = 0;
        goto LABEL_18;
      }
      UnattendLogW(0, L"ApplyOemToolsCallback: -> Target exists but is a directory, processing recursively");
    }
    *a3 = 1;
LABEL_18:
    if ( a2 )
    {
      v14 = -1;
      do
        ++v14;
      while ( a2[v14] );
      if ( v14 >= 0xF && CompareStringW(0x409u, 1u, &a2[v14 - 15], -1, L"winreconfig.xml", -1) == 2 )
        a4[2] = 1;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800415c0  push    rbx
0x1800415c2  push    rbp
0x1800415c3  push    rsi
0x1800415c4  push    rdi
0x1800415c5  push    r12
0x1800415c7  push    r14
0x1800415c9  sub     rsp, 38h
0x1800415cd  xor     ebp, ebp
0x1800415cf  mov     r14, r9
0x1800415d2  mov     rdi, r8
0x1800415d5  mov     rbx, rdx
0x1800415d8  test    ecx, ecx
0x1800415da  jz      loc_1800416DA
0x1800415e0  mov     esi, ebp
0x1800415e2  cmp     ecx, 9479h
0x1800415e8  jnz     loc_1800416DF
0x1800415ee  mov     rdx, [r9]; String2
0x1800415f1  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800415f5  mov     rax, r12
0x1800415f8  inc     rax
0x1800415fb  cmp     [rdx+rax*2], bp
0x1800415ff  jnz     short loc_1800415F8
0x180041601  mov     rcx, r12
0x180041604  inc     rcx
0x180041607  cmp     [rbx+rcx*2], bp
0x18004160b  jnz     short loc_180041604
0x18004160d  cmp     rcx, rax
0x180041610  mov     r9, rdx
0x180041613  mov     r8, r12
0x180041616  cmovb   r9, rbx
0x18004161a  inc     r8; MaxCount
0x18004161d  cmp     [r9+r8*2], bp
0x180041622  jnz     short loc_18004161A
0x180041624  mov     rcx, rbx; String1
0x180041627  call    cs:__imp__wcsnicmp
0x18004162d  test    eax, eax
0x18004162f  jz      short loc_180041638
0x180041631  mov     [rdi], ebp
0x180041633  jmp     loc_1800416DF
0x180041638  mov     r8, rbx
0x18004163b  lea     rdx, aApplyoemtoolsc; "ApplyOemToolsCallback: Deciding whether"...
0x180041642  xor     ecx, ecx
0x180041644  call    UnattendLogW
0x180041649  mov     rcx, rbx; lpFileName
0x18004164c  call    cs:__imp_GetFileAttributesW
0x180041652  xor     ecx, ecx
0x180041654  cmp     eax, 0FFFFFFFFh
0x180041657  jnz     short loc_180041662
0x180041659  lea     rdx, aApplyoemtoolsc_1; "ApplyOemToolsCallback: -> Target does n"...
0x180041660  jmp     short loc_18004166D
0x180041662  test    al, 10h
0x180041664  jz      short loc_18004167A
0x180041666  lea     rdx, aApplyoemtoolsc_0; "ApplyOemToolsCallback: -> Target exists"...
0x18004166d  call    UnattendLogW
0x180041672  mov     dword ptr [rdi], 1
0x180041678  jmp     short loc_180041688
0x18004167a  lea     rdx, aApplyoemtoolsc_2; "ApplyOemToolsCallback: -> Target file a"...
0x180041681  call    UnattendLogW
0x180041686  mov     [rdi], ebp
0x180041688  test    rbx, rbx
0x18004168b  jz      short loc_1800416DF
0x18004168d  mov     rax, r12
0x180041690  inc     rax
0x180041693  cmp     [rbx+rax*2], bp
0x180041697  jnz     short loc_180041690
0x180041699  cmp     rax, 0Fh
0x18004169d  jb      short loc_1800416DF
0x18004169f  add     rax, 0FFFFFFFFFFFFFFF1h
0x1800416a3  mov     [rsp+68h+cchCount2], r12d; cchCount2
0x1800416a8  mov     r9d, r12d; cchCount1
0x1800416ab  mov     edx, 1; dwCmpFlags
0x1800416b0  mov     ecx, 409h; Locale
0x1800416b5  lea     r8, [rbx+rax*2]; lpString1
0x1800416b9  lea     rax, aWinreconfigXml; "winreconfig.xml"
0x1800416c0  mov     [rsp+68h+lpString2], rax; lpString2
0x1800416c5  call    cs:__imp_CompareStringW
0x1800416cb  cmp     eax, 2
0x1800416ce  jnz     short loc_1800416DF
0x1800416d0  mov     dword ptr [r14+8], 1
0x1800416d8  jmp     short loc_1800416DF
0x1800416da  mov     esi, 57h ; 'W'
0x1800416df  mov     eax, esi
0x1800416e1  add     rsp, 38h
0x1800416e5  pop     r14
0x1800416e7  pop     r12
0x1800416e9  pop     rdi
0x1800416ea  pop     rsi
0x1800416eb  pop     rbp
0x1800416ec  pop     rbx
0x1800416ed  retn
```
