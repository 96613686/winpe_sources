# RetailDemoUtil::GetRetailDemoOriginRegistryLocation(ulong,ushort *,ushort const *)

- ea: `0x180030de0`
- end: `0x180030ef7`
- name: `?GetRetailDemoOriginRegistryLocation@RetailDemoUtil@@YAJKPEAGPEBG@Z`
- size: `279`
- prototype: `int(RetailDemoUtil *__hidden this, unsigned int, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001e238`
- `0x18002fa88`
- `0x180031ca0`

## callees

- `0x18000b148`
- `0x18000b1d4`
- `0x18001094c`
- `0x180030de0`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180030def`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180030def`
- `ntdll!RtlGetPersistedStateLocation` at `0x180030e25`
- `ntdll!RtlGetPersistedStateLocation` at `0x180030e25`
- `ntdll!RtlNtStatusToDosError` at `0x180030e2d`
- `ntdll!RtlNtStatusToDosError` at `0x180030e2d`

## string_xrefs

- `0x180030e48`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180030e71`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180030eab`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180030ed7`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`

## pseudocode

```c
__int64 __fastcall RetailDemoUtil::GetRetailDemoOriginRegistryLocation(
        RetailDemoUtil *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  NTSTATUS PersistedStateLocation; // eax
  signed int v7; // eax
  bool v8; // sf
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v13; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( (unsigned __int8)RtlIsStateSeparationEnabled(this, a2, a3, a4) )
  {
    v13 = (int)a2;
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"RetailDemo",
                               0,
                               L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo",
                               0);
    v7 = RtlNtStatusToDosError(PersistedStateLocation);
    v8 = v7 < 0;
    if ( v7 > 0 )
    {
      v7 = (unsigned __int16)v7 | 0x80070000;
      v8 = v7 < 0;
    }
    if ( v8 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
        (const char *)(unsigned int)v7,
        (int)a2);
  }
  else
  {
    v9 = StringCchCopyW(a2, 0x200u, L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo");
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
        (const char *)(unsigned int)v9,
        v13);
  }
  if ( a3 && *a3 )
  {
    v10 = StringCchCatW(a2, 0x200u, L"\\");
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
        (const char *)(unsigned int)v10,
        v13);
    v11 = StringCchCatW(a2, 0x200u, a3);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
        (const char *)(unsigned int)v11,
        v13);
  }
  return 0;
}

```

## disassembly

```asm
0x180030de0  push    rbx
0x180030de2  push    rbp
0x180030de3  push    rsi
0x180030de4  push    rdi
0x180030de5  sub     rsp, 48h
0x180030de9  mov     rbx, r8
0x180030dec  mov     rdi, rdx
0x180030def  call    cs:__imp_RtlIsStateSeparationEnabled
0x180030df5  xor     esi, esi
0x180030df7  lea     r8, ?c_retailDemoRootKey@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180030dfe  mov     ebp, 200h
0x180030e03  test    al, al
0x180030e05  jz      short loc_180030E5D
0x180030e07  mov     [rsp+68h+var_38], rsi
0x180030e0c  lea     rcx, ?c_retailDemoStateLocationSourceID@@3QBGB; "RetailDemo"
0x180030e13  mov     [rsp+68h+var_40], 400h
0x180030e1b  xor     r9d, r9d
0x180030e1e  xor     edx, edx
0x180030e20  mov     qword ptr [rsp+68h+var_48], rdi; int
0x180030e25  call    cs:__imp_RtlGetPersistedStateLocation
0x180030e2b  mov     ecx, eax; Status
0x180030e2d  call    cs:__imp_RtlNtStatusToDosError
0x180030e33  test    eax, eax
0x180030e35  jle     short loc_180030E41
0x180030e37  movzx   eax, ax
0x180030e3a  or      eax, 80070000h
0x180030e3f  test    eax, eax
0x180030e41  jns     short loc_180030E86
0x180030e43  mov     rcx, [rsp+68h]; this
0x180030e48  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030e4f  mov     r9d, eax; char *
0x180030e52  mov     edx, 66h ; 'f'; void *
0x180030e57  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030e5d  mov     rdx, rbp; unsigned __int64
0x180030e60  mov     rcx, rdi; unsigned __int16 *
0x180030e63  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030e68  test    eax, eax
0x180030e6a  jns     short loc_180030E86
0x180030e6c  mov     rcx, [rsp+68h]; this
0x180030e71  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030e78  mov     r9d, eax; char *
0x180030e7b  mov     edx, 6Ah ; 'j'; void *
0x180030e80  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030e86  test    rbx, rbx
0x180030e89  jz      short loc_180030EEC
0x180030e8b  cmp     [rbx], si
0x180030e8e  jz      short loc_180030EEC
0x180030e90  lea     r8, asc_180057BD8; "\\"
0x180030e97  mov     rdx, rbp; unsigned __int64
0x180030e9a  mov     rcx, rdi; unsigned __int16 *
0x180030e9d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180030ea2  test    eax, eax
0x180030ea4  jns     short loc_180030EC0
0x180030ea6  mov     rcx, [rsp+68h]; this
0x180030eab  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030eb2  mov     r9d, eax; char *
0x180030eb5  mov     edx, 6Fh ; 'o'; void *
0x180030eba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030ec0  mov     r8, rbx; unsigned __int16 *
0x180030ec3  mov     rdx, rbp; unsigned __int64
0x180030ec6  mov     rcx, rdi; unsigned __int16 *
0x180030ec9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180030ece  test    eax, eax
0x180030ed0  jns     short loc_180030EEC
0x180030ed2  mov     rcx, [rsp+68h]; this
0x180030ed7  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030ede  mov     r9d, eax; char *
0x180030ee1  mov     edx, 70h ; 'p'; void *
0x180030ee6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030eec  xor     eax, eax
0x180030eee  add     rsp, 48h
0x180030ef2  pop     rdi
0x180030ef3  pop     rsi
0x180030ef4  pop     rbp
0x180030ef5  pop     rbx
0x180030ef6  retn
```
