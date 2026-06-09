# WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper::RuntimeClassInitialize(WindowsInternal::Shell::UnifiedTile::ITileVerb *,HSTRING__ *,HSTRING__ *,bool)

- ea: `0x1800be7b0`
- end: `0x1800bea3c`
- name: `?RuntimeClassInitialize@TileVerbWrapper@Private@UnifiedTile@Shell@WindowsInternal@@QEAAJPEAUITileVerb@345@PEAUHSTRING__@@1_N@Z`
- size: `652`
- prototype: `int(WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper *__hidden this, struct WindowsInternal::Shell::UnifiedTile::ITileVerb *, HSTRING, HSTRING, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800be218`

## callees

- `0x18001aca4`
- `0x180021b78`
- `0x1800be7b0`
- `0x1800bea44`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800be81c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800be850`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800be81c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800be850`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be809`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be83d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be86e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be8cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be8ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be93c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be96b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be9e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be809`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be83d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be86e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be8cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be8ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be93c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be96b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be9e8`

## string_xrefs

- `0x1800be995`: `ShellCommon\private\Shell\inc\TileVerbWrapper.h`

## pseudocode

```c
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper::RuntimeClassInitialize(
        HSTRING *this,
        struct WindowsInternal::Shell::UnifiedTile::ITileVerb *a2,
        HSTRING a3,
        HSTRING a4,
        bool a5)
{
  __int64 v9; // rax
  HRESULT v10; // ebx
  HSTRING *v11; // rbx
  HSTRING *v12; // rbx
  __int64 (__fastcall *v13)(struct WindowsInternal::Shell::UnifiedTile::ITileVerb *, HSTRING *); // rdi
  __int64 (__fastcall *v14)(struct WindowsInternal::Shell::UnifiedTile::ITileVerb *, HSTRING *); // rdi
  __int64 (__fastcall *v15)(struct WindowsInternal::Shell::UnifiedTile::ITileVerb *, HSTRING *); // rbx
  __int64 (__fastcall *v16)(struct WindowsInternal::Shell::UnifiedTile::ITileVerb *, HSTRING *); // rdi
  __int64 (__fastcall *v17)(struct WindowsInternal::Shell::UnifiedTile::ITileVerb *, HSTRING *); // rdi
  __int64 v19; // rdx
  __int64 (__fastcall *v20)(struct WindowsInternal::Shell::UnifiedTile::ITileVerb *, HSTRING *); // rdi
  int v21; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char *v23; // [rsp+40h] [rbp+8h] BYREF

  v23 = (char *)(this + 18);
  v9 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v23);
  v10 = Microsoft::WRL::AsAgile<WindowsInternal::Shell::UnifiedTile::ITileVerb>(a2, v9);
  if ( v10 < 0 )
  {
    v19 = 41;
  }
  else
  {
    v11 = this + 8;
    if ( !a3 || a3 != *v11 )
    {
      WindowsDeleteString(*v11);
      *v11 = 0;
      v10 = WindowsDuplicateString(a3, this + 8);
      if ( v10 < 0 )
      {
        v19 = 43;
        goto LABEL_18;
      }
    }
    v12 = this + 9;
    if ( !a4 || a4 != *v12 )
    {
      WindowsDeleteString(*v12);
      *v12 = 0;
      v10 = WindowsDuplicateString(a4, this + 9);
      if ( v10 < 0 )
      {
        v19 = 44;
        goto LABEL_18;
      }
    }
    v13 = *(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::ITileVerb *, HSTRING *))(*(_QWORD *)a2 + 64LL);
    WindowsDeleteString(this[10]);
    this[10] = 0;
    v10 = v13(a2, this + 10);
    if ( v10 < 0 )
    {
      v19 = 45;
      goto LABEL_18;
    }
    v10 = (*(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::ITileVerb *, char *))(*(_QWORD *)a2 + 112LL))(
            a2,
            (char *)this + 136);
    if ( v10 < 0 )
    {
      v19 = 46;
    }
    else
    {
      if ( a5 )
        return 0;
      v14 = *(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::ITileVerb *, HSTRING *))(*(_QWORD *)a2 + 72LL);
      WindowsDeleteString(this[11]);
      this[11] = 0;
      v10 = v14(a2, this + 11);
      if ( v10 < 0 )
      {
        v19 = 50;
        goto LABEL_18;
      }
      v15 = *(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::ITileVerb *, HSTRING *))(*(_QWORD *)a2 + 80LL);
      WindowsDeleteString(this[12]);
      this[12] = 0;
      v10 = v15(a2, this + 12);
      if ( v10 < 0 )
      {
        v19 = 51;
      }
      else
      {
        if ( this[12] )
        {
          v20 = *(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::ITileVerb *, HSTRING *))(*(_QWORD *)a2 + 88LL);
          WindowsDeleteString(this[13]);
          this[13] = 0;
          v10 = v20(a2, this + 13);
          if ( v10 < 0 )
          {
            v19 = 54;
            goto LABEL_18;
          }
        }
        v16 = *(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::ITileVerb *, HSTRING *))(*(_QWORD *)a2 + 96LL);
        WindowsDeleteString(this[14]);
        this[14] = 0;
        v10 = v16(a2, this + 14);
        if ( v10 < 0 )
        {
          v19 = 56;
        }
        else
        {
          v17 = *(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::ITileVerb *, HSTRING *))(*(_QWORD *)a2 + 104LL);
          WindowsDeleteString(this[15]);
          this[15] = 0;
          v10 = v17(a2, this + 15);
          if ( v10 >= 0 )
            return 0;
          v19 = 57;
        }
      }
    }
  }
LABEL_18:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v19,
    (unsigned int)"ShellCommon\\private\\Shell\\inc\\TileVerbWrapper.h",
    (const char *)(unsigned int)v10,
    v21);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800be7b0  mov     r11, rsp
0x1800be7b3  mov     [r11+10h], rbx
0x1800be7b7  mov     [r11+18h], rbp
0x1800be7bb  push    rsi
0x1800be7bc  push    rdi
0x1800be7bd  push    r14; int
0x1800be7bf  sub     rsp, 20h
0x1800be7c3  mov     rdi, r9
0x1800be7c6  mov     r14, r8
0x1800be7c9  mov     rsi, rdx
0x1800be7cc  mov     rbp, rcx
0x1800be7cf  lea     rax, [rcx+90h]
0x1800be7d6  mov     [r11+8], rax
0x1800be7da  lea     rcx, [r11+8]
0x1800be7de  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x1800be7e3  mov     rdx, rax
0x1800be7e6  mov     rcx, rsi
0x1800be7e9  call    ??$AsAgile@UITileVerb@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@YAJPEAUITileVerb@UnifiedTile@Shell@WindowsInternal@@PEAVAgileRef@01@@Z; Microsoft::WRL::AsAgile<WindowsInternal::Shell::UnifiedTile::ITileVerb>(WindowsInternal::Shell::UnifiedTile::ITileVerb *,Microsoft::WRL::AgileRef *)
0x1800be7ee  mov     ebx, eax
0x1800be7f0  test    eax, eax
0x1800be7f2  js      loc_1800BE9CC
0x1800be7f8  lea     rbx, [rbp+40h]
0x1800be7fc  test    r14, r14
0x1800be7ff  jz      short loc_1800BE806
0x1800be801  cmp     r14, [rbx]
0x1800be804  jz      short loc_1800BE82C
0x1800be806  mov     rcx, [rbx]; string
0x1800be809  call    cs:__imp_WindowsDeleteString
0x1800be80f  mov     qword ptr [rbx], 0
0x1800be816  mov     rdx, rbx; newString
0x1800be819  mov     rcx, r14; string
0x1800be81c  call    cs:__imp_WindowsDuplicateString
0x1800be822  mov     ebx, eax
0x1800be824  test    eax, eax
0x1800be826  js      loc_1800BEA28
0x1800be82c  lea     rbx, [rbp+48h]
0x1800be830  test    rdi, rdi
0x1800be833  jz      short loc_1800BE83A
0x1800be835  cmp     rdi, [rbx]
0x1800be838  jz      short loc_1800BE860
0x1800be83a  mov     rcx, [rbx]; string
0x1800be83d  call    cs:__imp_WindowsDeleteString
0x1800be843  mov     qword ptr [rbx], 0
0x1800be84a  mov     rdx, rbx; newString
0x1800be84d  mov     rcx, rdi; string
0x1800be850  call    cs:__imp_WindowsDuplicateString
0x1800be856  mov     ebx, eax
0x1800be858  test    eax, eax
0x1800be85a  js      loc_1800BEA32
0x1800be860  mov     rax, [rsi]
0x1800be863  mov     rdi, [rax+40h]
0x1800be867  lea     rbx, [rbp+50h]
0x1800be86b  mov     rcx, [rbx]; string
0x1800be86e  call    cs:__imp_WindowsDeleteString
0x1800be874  mov     qword ptr [rbx], 0
0x1800be87b  mov     rdx, rbx
0x1800be87e  mov     rcx, rsi
0x1800be881  mov     rax, rdi
0x1800be884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be889  mov     ebx, eax
0x1800be88b  test    eax, eax
0x1800be88d  js      loc_1800BEA1E
0x1800be893  mov     rax, [rsi]
0x1800be896  lea     rdx, [rbp+88h]
0x1800be89d  mov     rcx, rsi
0x1800be8a0  mov     rax, [rax+70h]
0x1800be8a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be8a9  mov     ebx, eax
0x1800be8ab  test    eax, eax
0x1800be8ad  js      loc_1800BE9C5
0x1800be8b3  cmp     [rsp+38h+arg_20], 0
0x1800be8b8  jnz     loc_1800BE98C
0x1800be8be  mov     rax, [rsi]
0x1800be8c1  mov     rdi, [rax+48h]
0x1800be8c5  lea     rbx, [rbp+58h]
0x1800be8c9  mov     rcx, [rbx]; string
0x1800be8cc  call    cs:__imp_WindowsDeleteString
0x1800be8d2  mov     qword ptr [rbx], 0
0x1800be8d9  mov     rdx, rbx
0x1800be8dc  mov     rcx, rsi
0x1800be8df  mov     rax, rdi
0x1800be8e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be8e7  mov     ebx, eax
0x1800be8e9  test    eax, eax
0x1800be8eb  js      loc_1800BEA14
0x1800be8f1  mov     rax, [rsi]
0x1800be8f4  mov     rbx, [rax+50h]
0x1800be8f8  lea     rdi, [rbp+60h]
0x1800be8fc  mov     rcx, [rdi]; string
0x1800be8ff  call    cs:__imp_WindowsDeleteString
0x1800be905  mov     qword ptr [rdi], 0
0x1800be90c  mov     rdx, rdi
0x1800be90f  mov     rcx, rsi
0x1800be912  mov     rax, rbx
0x1800be915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be91a  mov     ebx, eax
0x1800be91c  test    eax, eax
0x1800be91e  js      loc_1800BE9BE
0x1800be924  cmp     qword ptr [rdi], 0
0x1800be928  jnz     loc_1800BE9DA
0x1800be92e  mov     rax, [rsi]
0x1800be931  mov     rdi, [rax+60h]
0x1800be935  lea     rbx, [rbp+70h]
0x1800be939  mov     rcx, [rbx]; string
0x1800be93c  call    cs:__imp_WindowsDeleteString
0x1800be942  mov     qword ptr [rbx], 0
0x1800be949  mov     rdx, rbx
0x1800be94c  mov     rcx, rsi
0x1800be94f  mov     rax, rdi
0x1800be952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be957  mov     ebx, eax
0x1800be959  test    eax, eax
0x1800be95b  js      short loc_1800BE990
0x1800be95d  mov     rax, [rsi]
0x1800be960  mov     rdi, [rax+68h]
0x1800be964  lea     rbx, [rbp+78h]
0x1800be968  mov     rcx, [rbx]; string
0x1800be96b  call    cs:__imp_WindowsDeleteString
0x1800be971  mov     qword ptr [rbx], 0
0x1800be978  mov     rdx, rbx
0x1800be97b  mov     rcx, rsi
0x1800be97e  mov     rax, rdi
0x1800be981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be986  mov     ebx, eax
0x1800be988  test    eax, eax
0x1800be98a  js      short loc_1800BE9D3
0x1800be98c  xor     eax, eax
0x1800be98e  jmp     short loc_1800BE9AB
0x1800be990  mov     edx, 38h ; '8'; void *
0x1800be995  lea     r8, aShellcommonPri; "ShellCommon\\private\\Shell\\inc\\TileV"...
0x1800be99c  mov     r9d, ebx; char *
0x1800be99f  mov     rcx, [rsp+38h]; this
0x1800be9a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be9a9  mov     eax, ebx
0x1800be9ab  mov     rbx, [rsp+38h+arg_8]
0x1800be9b0  mov     rbp, [rsp+38h+arg_10]
0x1800be9b5  add     rsp, 20h
0x1800be9b9  pop     r14
0x1800be9bb  pop     rdi
0x1800be9bc  pop     rsi
0x1800be9bd  retn
0x1800be9be  mov     edx, 33h ; '3'
0x1800be9c3  jmp     short loc_1800BE995
0x1800be9c5  mov     edx, 2Eh ; '.'
0x1800be9ca  jmp     short loc_1800BE995
0x1800be9cc  mov     edx, 29h ; ')'
0x1800be9d1  jmp     short loc_1800BE995
0x1800be9d3  mov     edx, 39h ; '9'
0x1800be9d8  jmp     short loc_1800BE995
0x1800be9da  mov     rax, [rsi]
0x1800be9dd  mov     rdi, [rax+58h]
0x1800be9e1  lea     rbx, [rbp+68h]
0x1800be9e5  mov     rcx, [rbx]; string
0x1800be9e8  call    cs:__imp_WindowsDeleteString
0x1800be9ee  mov     qword ptr [rbx], 0
0x1800be9f5  mov     rdx, rbx
0x1800be9f8  mov     rcx, rsi
0x1800be9fb  mov     rax, rdi
0x1800be9fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bea03  mov     ebx, eax
0x1800bea05  test    eax, eax
0x1800bea07  jns     loc_1800BE92E
0x1800bea0d  mov     edx, 36h ; '6'
0x1800bea12  jmp     short loc_1800BE995
0x1800bea14  mov     edx, 32h ; '2'
0x1800bea19  jmp     loc_1800BE995
0x1800bea1e  mov     edx, 2Dh ; '-'
0x1800bea23  jmp     loc_1800BE995
0x1800bea28  mov     edx, 2Bh ; '+'
0x1800bea2d  jmp     loc_1800BE995
0x1800bea32  mov     edx, 2Ch ; ','
0x1800bea37  jmp     loc_1800BE995
```
