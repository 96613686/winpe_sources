# InitPerformanceDLLEx(Microsoft::Internal::Performance::CodeMarkerApp,ushort const *,bool,Microsoft::Internal::Performance::CodeMarkerEvent,bool)

- ea: `0x1400134ac`
- end: `0x140013709`
- name: `?InitPerformanceDLLEx@@YAXW4CodeMarkerApp@Performance@Internal@Microsoft@@PEBG_NW4CodeMarkerEvent@234@2@Z`
- size: `605`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140001388`

## callees

- `0x1400130c0`
- `0x1400131f0`
- `0x140013270`
- `0x140013410`
- `0x1400134ac`
- `0x1400137e0`
- `0x140014b10`
- `0x140014b20`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x140013611`
- `KERNEL32!GetFileAttributesW` at `0x140013611`
- `KERNEL32!LoadLibraryW` at `0x140013625`
- `KERNEL32!LoadLibraryW` at `0x140013625`
- `KERNEL32!GetModuleFileNameW` at `0x140013576`
- `KERNEL32!GetModuleFileNameW` at `0x140013576`
- `KERNEL32!AddAtomW` at `0x14001366f`
- `KERNEL32!AddAtomW` at `0x140013693`
- `KERNEL32!AddAtomW` at `0x14001366f`
- `KERNEL32!AddAtomW` at `0x140013693`

## pseudocode

```c
void __fastcall InitPerformanceDLLEx(int a1, unsigned __int16 *a2, __int64 a3, unsigned int a4, char a5)
{
  signed __int64 v8; // rdx
  wchar_t *v9; // rcx
  __int64 v10; // rbx
  wchar_t v11; // ax
  bool v12; // zf
  wchar_t *v13; // rax
  HMODULE LibraryW; // rax
  unsigned int v15; // eax
  unsigned int v16; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Drive[6]; // [rsp+54h] [rbp-ACh] BYREF
  wchar_t Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Dir[256]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR Filename[264]; // [rsp+470h] [rbp+370h] BYREF
  wchar_t Ext[256]; // [rsp+680h] [rbp+580h] BYREF
  wchar_t v22[256]; // [rsp+880h] [rbp+780h] BYREF

  if ( a2 && !ghInstPerf )
  {
    if ( (unsigned __int8)FEnabledInRegistry(a2) )
    {
      v8 = (char *)off_140023020 - (char *)Buffer;
      v9 = Buffer;
      v10 = 260;
      do
      {
        if ( v10 == -2147483386 )
          break;
        v11 = *(wchar_t *)((char *)v9 + v8);
        if ( !v11 )
          break;
        *v9++ = v11;
        --v10;
      }
      while ( v10 );
      v12 = v10 == 0;
      v13 = v9 - 1;
      if ( v10 )
        v13 = v9;
      *v13 = 0;
    }
    else
    {
      if ( !a5
        || (GetModuleFileNameW(0, Filename, 0x104u) & 0x80000000) != 0
        || wsplitpath_s_0(Filename, Drive, 3u, Dir, 0x100u, v22, 0x100u, Ext, 0x100u)
        || wmakepath_s_0(Buffer, 0x104u, Drive, Dir, ::Filename, L".dll") )
      {
        return;
      }
      v12 = GetFileAttributesW(Buffer) == -1;
    }
    if ( !v12 )
    {
      LibraryW = LoadLibraryW(Buffer);
      if ( LibraryW )
      {
        Attach(LibraryW);
        if ( gpSetPerformanceRegRoot )
          gpSetPerformanceRegRoot(a2);
        if ( gpfCodeMarker && gpfUnInitPerf )
        {
          if ( gpfInitPerf2 )
          {
            AddAtomW(lpString);
            gpfInitPerf2(a1, a2);
          }
          else if ( gpfInitPerf )
          {
            AddAtomW(lpString);
            gpfInitPerf(a1);
          }
        }
        v16 = 0;
        if ( GetPerformanceRegistryDwordValue(HKEY_LOCAL_MACHINE, a2, L"AutoStartupLoggingEndMarker", &v16) )
        {
          v15 = 0;
          v16 = 0;
        }
        else
        {
          v15 = v16;
        }
        if ( v15 )
          a4 = v15;
        if ( a4 )
          BeginCodeMarkerLogging(a4);
      }
    }
  }
}

```

## disassembly

```asm
0x1400134ac  test    rdx, rdx
0x1400134af  jz      locret_140013708
0x1400134b5  mov     [rsp-8+arg_10], rbx
0x1400134ba  push    rbp
0x1400134bb  push    rsi
0x1400134bc  push    rdi
0x1400134bd  push    r14
0x1400134bf  push    r15
0x1400134c1  lea     rbp, [rsp-990h]
0x1400134c9  sub     rsp, 0A90h
0x1400134d0  mov     rax, cs:__security_cookie
0x1400134d7  xor     rax, rsp
0x1400134da  mov     [rbp+9B0h+var_30], rax
0x1400134e1  xor     r15d, r15d
0x1400134e4  mov     edi, r9d
0x1400134e7  cmp     cs:?ghInstPerf@@3PEAUHINSTANCE__@@EA, r15; HINSTANCE__ * ghInstPerf
0x1400134ee  mov     rsi, rdx
0x1400134f1  mov     r14d, ecx
0x1400134f4  jnz     loc_1400136E3
0x1400134fa  mov     dl, r8b
0x1400134fd  mov     rcx, rsi; unsigned __int16 *
0x140013500  call    FEnabledInRegistry
0x140013505  test    al, al
0x140013507  jz      short loc_140013558
0x140013509  mov     rdx, cs:off_140023020; "Microsoft.Internal.Performance.CodeMark"...
0x140013510  lea     rax, [rsp+0AB0h+Buffer]
0x140013515  sub     rdx, rax
0x140013518  lea     rcx, [rsp+0AB0h+Buffer]
0x14001351d  mov     ebx, 104h
0x140013522  lea     rax, [rbx+7FFFFEFAh]
0x140013529  test    rax, rax
0x14001352c  jz      short loc_140013544
0x14001352e  movzx   eax, word ptr [rdx+rcx]
0x140013532  test    ax, ax
0x140013535  jz      short loc_140013544
0x140013537  mov     [rcx], ax
0x14001353a  add     rcx, 2
0x14001353e  sub     rbx, 1
0x140013542  jnz     short loc_140013522
0x140013544  test    rbx, rbx
0x140013547  lea     rax, [rcx-2]
0x14001354b  cmovnz  rax, rcx
0x14001354f  mov     [rax], r15w
0x140013553  jmp     loc_14001361A
0x140013558  cmp     [rbp+9B0h+arg_20], r15b
0x14001355f  jz      loc_1400136E3
0x140013565  mov     ebx, 104h
0x14001356a  lea     rdx, [rbp+9B0h+Filename]; lpFilename
0x140013571  mov     r8d, ebx; nSize
0x140013574  xor     ecx, ecx; hModule
0x140013576  call    cs:__imp_GetModuleFileNameW
0x14001357c  test    eax, eax
0x14001357e  js      loc_1400136E3
0x140013584  lea     ecx, [rbx-4]
0x140013587  mov     r8d, 3; DriveCount
0x14001358d  mov     [rsp+0AB0h+ExtCount], rcx; ExtCount
0x140013592  lea     rax, [rbp+9B0h+var_430]
0x140013599  mov     [rsp+0AB0h+Ext], rax; Ext
0x14001359e  lea     r9, [rbp+9B0h+Dir]; Dir
0x1400135a5  mov     [rsp+0AB0h+FilenameCount], rcx; FilenameCount
0x1400135aa  lea     rax, [rbp+9B0h+var_230]
0x1400135b1  mov     [rsp+0AB0h+var_A88], rax; Filename
0x1400135b6  lea     rdx, [rsp+0AB0h+Drive]; Drive
0x1400135bb  mov     [rsp+0AB0h+DirCount], rcx; DirCount
0x1400135c0  lea     rcx, [rbp+9B0h+Filename]; FullPath
0x1400135c7  call    _wsplitpath_s_0
0x1400135cc  test    eax, eax
0x1400135ce  jnz     loc_1400136E3
0x1400135d4  lea     rax, aDll; ".dll"
0x1400135db  mov     edx, ebx; BufferCount
0x1400135dd  mov     [rsp+0AB0h+var_A88], rax; Ext
0x1400135e2  lea     r9, [rbp+9B0h+Dir]; Dir
0x1400135e9  mov     rax, cs:Filename
0x1400135f0  lea     r8, [rsp+0AB0h+Drive]; Drive
0x1400135f5  lea     rcx, [rsp+0AB0h+Buffer]; Buffer
0x1400135fa  mov     [rsp+0AB0h+DirCount], rax; Filename
0x1400135ff  call    _wmakepath_s_0
0x140013604  test    eax, eax
0x140013606  jnz     loc_1400136E3
0x14001360c  lea     rcx, [rsp+0AB0h+Buffer]; lpFileName
0x140013611  call    cs:__imp_GetFileAttributesW
0x140013617  cmp     eax, 0FFFFFFFFh
0x14001361a  jz      loc_1400136E3
0x140013620  lea     rcx, [rsp+0AB0h+Buffer]; lpLibFileName
0x140013625  call    cs:__imp_LoadLibraryW
0x14001362b  test    rax, rax
0x14001362e  jz      loc_1400136E3
0x140013634  mov     rcx, rax; hModule
0x140013637  call    Attach
0x14001363c  mov     rax, cs:?gpSetPerformanceRegRoot@@3P6AXPEBG@ZEA; void (*gpSetPerformanceRegRoot)(ushort const *)
0x140013643  test    rax, rax
0x140013646  jz      short loc_14001364D
0x140013648  mov     rcx, rsi
0x14001364b  call    rax ; void (*gpSetPerformanceRegRoot)(ushort const *)
0x14001364d  cmp     cs:?gpfCodeMarker@@3P6AXHPEBXK@ZEA, r15; void (*gpfCodeMarker)(int,void const *,ulong)
0x140013654  jz      short loc_1400136A2
0x140013656  cmp     cs:?gpfUnInitPerf@@3P6AXH@ZEA, r15; void (*gpfUnInitPerf)(int)
0x14001365d  jz      short loc_1400136A2
0x14001365f  cmp     cs:?gpfInitPerf2@@3P6AXHPEBG@ZEA, r15; void (*gpfInitPerf2)(int,ushort const *)
0x140013666  jz      short loc_140013683
0x140013668  mov     rcx, cs:lpString; lpString
0x14001366f  call    cs:__imp_AddAtomW
0x140013675  mov     rdx, rsi
0x140013678  mov     ecx, r14d
0x14001367b  call    cs:?gpfInitPerf2@@3P6AXHPEBG@ZEA; void (*gpfInitPerf2)(int,ushort const *)
0x140013681  jmp     short loc_1400136A2
0x140013683  cmp     cs:?gpfInitPerf@@3P6AXH@ZEA, r15; void (*gpfInitPerf)(int)
0x14001368a  jz      short loc_1400136A2
0x14001368c  mov     rcx, cs:lpString; lpString
0x140013693  call    cs:__imp_AddAtomW
0x140013699  mov     ecx, r14d
0x14001369c  call    cs:?gpfInitPerf@@3P6AXH@ZEA; void (*gpfInitPerf)(int)
0x1400136a2  lea     r9, [rsp+0AB0h+var_A60]; unsigned int *
0x1400136a7  mov     [rsp+0AB0h+var_A60], r15d
0x1400136ac  lea     r8, aAutostartuplog; "AutoStartupLoggingEndMarker"
0x1400136b3  mov     rdx, rsi; unsigned __int16 *
0x1400136b6  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1400136bd  call    ?GetPerformanceRegistryDwordValue@@YAJPEAUHKEY__@@PEBG1AEAK@Z; GetPerformanceRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong &)
0x1400136c2  test    eax, eax
0x1400136c4  jz      short loc_1400136CF
0x1400136c6  mov     eax, r15d
0x1400136c9  mov     [rsp+0AB0h+var_A60], eax
0x1400136cd  jmp     short loc_1400136D3
0x1400136cf  mov     eax, [rsp+0AB0h+var_A60]
0x1400136d3  test    eax, eax
0x1400136d5  cmovnz  edi, eax
0x1400136d8  test    edi, edi
0x1400136da  jz      short loc_1400136E3
0x1400136dc  mov     ecx, edi
0x1400136de  call    ?BeginCodeMarkerLogging@@YAJW4CodeMarkerEvent@Performance@Internal@Microsoft@@@Z; BeginCodeMarkerLogging(Microsoft::Internal::Performance::CodeMarkerEvent)
0x1400136e3  mov     rcx, [rbp+9B0h+var_30]
0x1400136ea  xor     rcx, rsp; StackCookie
0x1400136ed  call    __security_check_cookie
0x1400136f2  mov     rbx, [rsp+0AB0h+arg_10]
0x1400136fa  add     rsp, 0A90h
0x140013701  pop     r15
0x140013703  pop     r14
0x140013705  pop     rdi
0x140013706  pop     rsi
0x140013707  pop     rbp
0x140013708  retn
```
