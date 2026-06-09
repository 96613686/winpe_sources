# InitHotMofStuff(_PROG_RESOURCES *)

- ea: `0x1800099c8`
- end: `0x180009b11`
- name: `?InitHotMofStuff@@YAHPEAU_PROG_RESOURCES@@@Z`
- size: `329`
- prototype: `__int64 __fastcall(struct _PROG_RESOURCES *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800098a0`

## callees

- `0x180004c30`
- `0x1800099c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009ae4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009ae4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180009a52`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180009a52`
- `api-ms-win-core-file-l1-1-0!FindFirstChangeNotificationW` at `0x180009aca`
- `api-ms-win-core-file-l1-1-0!FindFirstChangeNotificationW` at `0x180009aca`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x180009a05`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x180009a05`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180009a9e`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180009af9`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180009a9e`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180009af9`
- `wbemcomn!?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z` at `0x180009a23`
- `wbemcomn!?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z` at `0x180009a23`
- `wbemcomn!?SetStr@Registry@@QEAAHPEBG0@Z` at `0x180009a85`
- `wbemcomn!?SetStr@Registry@@QEAAHPEBG0@Z` at `0x180009a85`
- `wbemcomn!TestDirExistAndCreateWithSDIfNotThere` at `0x180009ab7`
- `wbemcomn!TestDirExistAndCreateWithSDIfNotThere` at `0x180009ab7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800099e6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009a93`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800099e6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009a93`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009a37`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009a37`

## string_xrefs

- `0x180009a18`: `MOF Self-Install Directory`
- `0x180009a7a`: `MOF Self-Install Directory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall InitHotMofStuff(struct _PROG_RESOURCES *a1)
{
  void *v2; // rcx
  unsigned int v3; // edi
  unsigned __int16 *v4; // rax
  UINT SystemDirectoryW; // eax
  unsigned __int16 *v6; // rcx
  unsigned __int16 *v8; // rcx
  HANDLE v9; // rax
  HANDLE EventW; // rax
  _BYTE v11[32]; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v12; // [rsp+50h] [rbp+10h] BYREF

  v2 = (void *)*((_QWORD *)a1 + 12);
  if ( v2 )
  {
    CWin32DefaultArena::WbemMemFree(v2);
    *((_QWORD *)a1 + 12) = 0;
  }
  Registry::Registry((Registry *)v11, L"Software\\Microsoft\\WBEM\\CIMOM", 3u);
  v12 = 0;
  v3 = 1;
  if ( !Registry::GetStr((Registry *)v11, L"MOF Self-Install Directory", &v12) )
    goto LABEL_9;
  v4 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x21Cu);
  v12 = v4;
  if ( v4 )
  {
    SystemDirectoryW = GetSystemDirectoryW(v4, 0x105u);
    v6 = v12;
    if ( SystemDirectoryW - 1 > 0x103 )
    {
LABEL_8:
      CWin32DefaultArena::WbemMemFree(v6);
      Registry::~Registry((Registry *)v11);
      return 0;
    }
    StringCchCatW(v12, 0x10Eu, L"\\wbem\\mof");
    if ( Registry::SetStr((Registry *)v11, L"MOF Self-Install Directory", v12) == 1 )
    {
      v6 = v12;
      goto LABEL_8;
    }
LABEL_9:
    v8 = v12;
    *((_QWORD *)a1 + 12) = v12;
    if ( (int)TestDirExistAndCreateWithSDIfNotThere(v8, L"D:P(A;CIOI;GA;;;BA)(A;CIOI;GA;;;SY)") >= 0 )
    {
      v9 = FindFirstChangeNotificationW(*((LPCWSTR *)a1 + 12), 0, 1u);
      *((_QWORD *)a1 + 11) = v9;
      if ( v9 != (HANDLE)-1LL )
        goto LABEL_13;
      EventW = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)a1 + 11) = EventW;
      if ( EventW )
        goto LABEL_13;
    }
  }
  v3 = 0;
LABEL_13:
  Registry::~Registry((Registry *)v11);
  return v3;
}

```

## disassembly

```asm
0x1800099c8  mov     [rsp-8+arg_8], rbx
0x1800099cd  mov     [rsp-8+arg_10], rdi
0x1800099d2  push    rbp
0x1800099d3  mov     rbp, rsp
0x1800099d6  sub     rsp, 40h
0x1800099da  mov     rbx, rcx
0x1800099dd  mov     rcx, [rcx+60h]
0x1800099e1  test    rcx, rcx
0x1800099e4  jz      short loc_1800099F4
0x1800099e6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800099ec  mov     qword ptr [rbx+60h], 0
0x1800099f4  mov     r8d, 3
0x1800099fa  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\CIMOM"
0x180009a01  lea     rcx, [rbp+var_20]
0x180009a05  call    cs:__imp_??0Registry@@QEAA@PEBGK@Z; Registry::Registry(ushort const *,ulong)
0x180009a0b  nop
0x180009a0c  mov     [rbp+arg_0], 0
0x180009a14  lea     r8, [rbp+arg_0]
0x180009a18  lea     rdx, aMofSelfInstall; "MOF Self-Install Directory"
0x180009a1f  lea     rcx, [rbp+var_20]
0x180009a23  call    cs:__imp_?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z; Registry::GetStr(ushort const *,ushort * *)
0x180009a29  mov     edi, 1
0x180009a2e  test    eax, eax
0x180009a30  jz      short loc_180009AA8
0x180009a32  mov     ecx, 21Ch
0x180009a37  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180009a3d  mov     [rbp+arg_0], rax
0x180009a41  test    rax, rax
0x180009a44  jz      loc_180009AF3
0x180009a4a  mov     edx, 105h; uSize
0x180009a4f  mov     rcx, rax; lpBuffer
0x180009a52  call    cs:__imp_GetSystemDirectoryW
0x180009a58  dec     eax
0x180009a5a  mov     rcx, [rbp+arg_0]; unsigned __int16 *
0x180009a5e  cmp     eax, 103h
0x180009a63  ja      short loc_180009A93
0x180009a65  lea     r8, aWbemMof; "\\wbem\\mof"
0x180009a6c  mov     edx, 10Eh; unsigned __int64
0x180009a71  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009a76  mov     r8, [rbp+arg_0]
0x180009a7a  lea     rdx, aMofSelfInstall; "MOF Self-Install Directory"
0x180009a81  lea     rcx, [rbp+var_20]
0x180009a85  call    cs:__imp_?SetStr@Registry@@QEAAHPEBG0@Z; Registry::SetStr(ushort const *,ushort const *)
0x180009a8b  cmp     eax, edi
0x180009a8d  jnz     short loc_180009AA8
0x180009a8f  mov     rcx, [rbp+arg_0]
0x180009a93  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180009a99  nop
0x180009a9a  lea     rcx, [rbp+var_20]
0x180009a9e  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x180009aa4  xor     eax, eax
0x180009aa6  jmp     short loc_180009B01
0x180009aa8  mov     rcx, [rbp+arg_0]
0x180009aac  mov     [rbx+60h], rcx
0x180009ab0  lea     rdx, aDPACioiGaBaACi; "D:P(A;CIOI;GA;;;BA)(A;CIOI;GA;;;SY)"
0x180009ab7  call    cs:__imp_?TestDirExistAndCreateWithSDIfNotThere@@YAJPEAG0@Z; TestDirExistAndCreateWithSDIfNotThere(ushort *,ushort *)
0x180009abd  test    eax, eax
0x180009abf  js      short loc_180009AF3
0x180009ac1  mov     r8d, edi; dwNotifyFilter
0x180009ac4  xor     edx, edx; bWatchSubtree
0x180009ac6  mov     rcx, [rbx+60h]; lpPathName
0x180009aca  call    cs:__imp_FindFirstChangeNotificationW
0x180009ad0  mov     [rbx+58h], rax
0x180009ad4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009ad8  jnz     short loc_180009AF5
0x180009ada  xor     r9d, r9d; lpName
0x180009add  xor     r8d, r8d; bInitialState
0x180009ae0  xor     edx, edx; bManualReset
0x180009ae2  xor     ecx, ecx; lpEventAttributes
0x180009ae4  call    cs:__imp_CreateEventW
0x180009aea  mov     [rbx+58h], rax
0x180009aee  test    rax, rax
0x180009af1  jnz     short loc_180009AF5
0x180009af3  xor     edi, edi
0x180009af5  lea     rcx, [rbp+var_20]
0x180009af9  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x180009aff  mov     eax, edi
0x180009b01  mov     rbx, [rsp+40h+arg_8]
0x180009b06  mov     rdi, [rsp+40h+arg_10]
0x180009b0b  add     rsp, 40h
0x180009b0f  pop     rbp
0x180009b10  retn
```
