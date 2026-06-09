# CTrace::RegQueryComponentTraceContext(HKEY__ *,ushort *,_TRACE_CONTEXT *)

- ea: `0x180015604`
- end: `0x18001599d`
- name: `?RegQueryComponentTraceContext@CTrace@@AEAAJPEAUHKEY__@@PEAGPEAU_TRACE_CONTEXT@@@Z`
- size: `921`
- prototype: `__int64 __fastcall(CTrace *__hidden this, HKEY, unsigned __int16 *, struct _TRACE_CONTEXT *)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180006420`
- `0x180015604`
- `0x180020830`

## callees

- `0x1800063b0`
- `0x18000fb90`
- `0x180015604`
- `0x1800159a4`
- `0x1800159d8`
- `0x180022e30`
- `0x1800240b0`
- `0x1800240f0`
- `0x1800240fc`
- `0x18009823c`
- `0x1800b8420`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180015924`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180015924`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001568f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001568f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015966`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015966`

## string_xrefs

- `0x1800156cd`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x180015728`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x180015844`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x1800156ab`: `Failed to open %ls subkey`
- `0x1800156bb`: `CTrace::RegQueryComponentTraceContext`
- `0x180015716`: `CTrace::RegQueryComponentTraceContext`
- `0x180015832`: `CTrace::RegQueryComponentTraceContext`
- `0x180015706`: `Failed to open UniqueId subkey`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CTrace::RegQueryComponentTraceContext(
        CTrace *this,
        HKEY a2,
        unsigned __int16 *a3,
        struct _TRACE_CONTEXT *a4)
{
  WCHAR *v8; // r14
  unsigned int v9; // esi
  LSTATUS v10; // eax
  int v11; // eax
  __int64 v12; // rax
  _DWORD *v13; // rax
  _DWORD *v14; // r13
  __int64 v15; // rbx
  void *v16; // rax
  __int64 v17; // rcx
  DWORD v18; // ebx
  LSTATUS v19; // r15d
  LPWSTR lpClass; // [rsp+28h] [rbp-A0h]
  unsigned int v22; // [rsp+40h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-80h] BYREF
  unsigned int v24; // [rsp+50h] [rbp-78h] BYREF
  DWORD cchName; // [rsp+54h] [rbp-74h] BYREF
  int v26[2]; // [rsp+58h] [rbp-70h] BYREF
  __int64 v27; // [rsp+60h] [rbp-68h]
  WCHAR *v28; // [rsp+68h] [rbp-60h]
  unsigned int v29[2]; // [rsp+70h] [rbp-58h] BYREF
  unsigned int v30; // [rsp+78h] [rbp-50h] BYREF

  *(_QWORD *)v29 = 0;
  v30 = 0;
  v24 = 0;
  v22 = 0;
  hKey = 0;
  cchName = 0;
  v8 = (WCHAR *)operator new[](0x608u);
  v28 = v8;
  if ( !v8 )
  {
    v9 = -2147024882;
    goto LABEL_24;
  }
  v10 = RegOpenKeyExW(a2, a3, 0, 0x20119u, &hKey);
  v9 = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
    LODWORD(lpClass) = v9;
    TraceStringInline(
      14,
      1,
      L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
      810,
      L"CTrace::RegQueryComponentTraceContext",
      lpClass,
      L"Failed to open %ls subkey",
      a3);
  }
  else
  {
    v11 = RegQueryDword(hKey, L"UniqueId", &v22, 0);
    v9 = v11;
    if ( v11 < 0 )
    {
      LODWORD(lpClass) = v11;
      TraceStringInline(
        14,
        1,
        L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
        819,
        L"CTrace::RegQueryComponentTraceContext",
        lpClass,
        L"Failed to open UniqueId subkey");
      goto LABEL_24;
    }
    if ( a4 )
    {
      RegQueryDword(hKey, L"Active", &v24, *(_DWORD *)a4);
      v29[0] = v24 & *(_DWORD *)a4;
      RegQueryDword(hKey, L"Level", &v29[1], *((_DWORD *)a4 + 1));
      RegQueryDword(hKey, L"ControlFlags", &v30, *((_DWORD *)a4 + 2));
    }
    else
    {
      RegQueryDword(hKey, L"Active", &v24, 1u);
      v29[0] = v24;
      RegQueryDword(hKey, L"Level", &v29[1], 0);
      RegQueryDword(hKey, L"ControlFlags", &v30, 0);
    }
    v12 = std::_Tree<std::_Tmap_traits<unsigned long,_TRACE_CONTEXT *,std::less<unsigned long>,throwing_allocator<_TRACE_CONTEXT *>,0>>::find(
            (char *)this + 1632,
            v26,
            &v22);
    if ( *(_QWORD *)v12 == *((_QWORD *)this + 204) )
    {
      v13 = operator new(0xCu);
      v14 = v13;
      if ( !v13 )
      {
        v9 = -2147024882;
        LODWORD(lpClass) = -2147024882;
        TraceStringInline(
          14,
          1,
          L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
          879,
          L"CTrace::RegQueryComponentTraceContext",
          lpClass,
          L"new TRACE_CONTEXT Failed");
        goto LABEL_24;
      }
      *(_QWORD *)v13 = *(_QWORD *)v29;
      v13[2] = v30;
      std::_Tree<std::_Tmap_traits<unsigned long,_TRACE_CONTEXT *,std::less<unsigned long>,throwing_allocator<_TRACE_CONTEXT *>,0>>::lower_bound(
        (char *)this + 1632,
        v26,
        &v22);
      v15 = *(_QWORD *)v26;
      if ( *(_QWORD *)v26 == *((_QWORD *)this + 204) || v22 < *(_DWORD *)(*(_QWORD *)v26 + 32LL) )
      {
        v26[0] = v22;
        v27 = 0;
        v16 = (void *)std::_Tree_buy<std::pair<unsigned long const,_TRACE_CONTEXT *>,throwing_allocator<_TRACE_CONTEXT *>>::_Buynode<std::pair<unsigned long,_TRACE_CONTEXT *>>(
                        (char *)this + 1632,
                        v26);
        std::_Tree<std::_Tmap_traits<unsigned long,_TRACE_CONTEXT *,std::less<unsigned long>,throwing_allocator<_TRACE_CONTEXT *>,0>>::_Insert_hint<std::pair<unsigned long const,_TRACE_CONTEXT *> &,std::_Tree_node<std::pair<unsigned long const,_TRACE_CONTEXT *>,void *> *>(
          (_DWORD)this + 1632,
          (int)v26,
          v15,
          v16);
        v15 = *(_QWORD *)v26;
      }
      *(_QWORD *)(v15 + 40) = v14;
    }
    else
    {
      v17 = *(_QWORD *)(*(_QWORD *)v12 + 40LL);
      *(_QWORD *)v17 = *(_QWORD *)v29;
      *(_DWORD *)(v17 + 8) = v30;
    }
    v18 = 0;
    do
    {
      cchName = 772;
      v19 = RegEnumKeyExW(hKey, v18, v8, &cchName, 0, 0, 0, 0);
      if ( !v19 )
        CTrace::RegQueryComponentTraceContext(this, hKey, v8, (struct _TRACE_CONTEXT *)v29);
      ++v18;
    }
    while ( v19 != 259 );
  }
LABEL_24:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v8 )
    operator delete(v8);
  return v9;
}

```

## disassembly

```asm
0x180015604  push    rbx
0x180015606  push    rsi
0x180015607  push    r12
0x180015609  push    r13
0x18001560b  push    r14
0x18001560d  push    r15
0x18001560f  sub     rsp, 98h
0x180015616  mov     rax, cs:__security_cookie
0x18001561d  xor     rax, rsp
0x180015620  mov     [rsp+0C8h+var_48], rax
0x180015628  mov     rbx, r9
0x18001562b  mov     r15, r8
0x18001562e  mov     rsi, rdx
0x180015631  mov     r12, rcx
0x180015634  xor     eax, eax
0x180015636  mov     qword ptr [rsp+0C8h+var_58], rax
0x18001563b  mov     [rsp+0C8h+var_50], eax
0x18001563f  mov     [rsp+0C8h+var_78], eax
0x180015643  mov     [rsp+0C8h+var_88], eax
0x180015647  mov     [rsp+0C8h+hKey], rax
0x18001564c  mov     [rsp+0C8h+var_60], rax
0x180015651  mov     [rsp+0C8h+cchName], eax
0x180015655  mov     ecx, 608h; unsigned __int64
0x18001565a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001565f  mov     r14, rax
0x180015662  mov     [rsp+0C8h+var_60], rax
0x180015667  test    rax, rax
0x18001566a  jnz     short loc_180015676
0x18001566c  mov     esi, 8007000Eh
0x180015671  jmp     loc_18001595C
0x180015676  lea     rax, [rsp+0C8h+hKey]
0x18001567b  mov     [rsp+0C8h+phkResult], rax; phkResult
0x180015680  mov     r9d, 20119h; samDesired
0x180015686  xor     r8d, r8d; ulOptions
0x180015689  mov     rdx, r15; lpSubKey
0x18001568c  mov     rcx, rsi; hKey
0x18001568f  call    cs:__imp_RegOpenKeyExW
0x180015695  mov     esi, eax
0x180015697  test    eax, eax
0x180015699  jz      short loc_1800156E7
0x18001569b  jle     short loc_1800156A6
0x18001569d  movzx   esi, ax
0x1800156a0  or      esi, 80070000h
0x1800156a6  mov     [rsp+0C8h+lpftLastWriteTime], r15
0x1800156ab  lea     rax, aFailedToOpenLs; "Failed to open %ls subkey"
0x1800156b2  mov     [rsp+0C8h+lpcchClass], rax
0x1800156b7  mov     dword ptr [rsp+0C8h+lpClass], esi
0x1800156bb  lea     rax, aCtraceRegquery; "CTrace::RegQueryComponentTraceContext"
0x1800156c2  mov     [rsp+0C8h+phkResult], rax
0x1800156c7  mov     r9d, 32Ah
0x1800156cd  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x1800156d4  mov     edx, 1
0x1800156d9  lea     ecx, [rdx+0Dh]
0x1800156dc  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800156e1  nop
0x1800156e2  jmp     loc_18001595C
0x1800156e7  xor     r9d, r9d; unsigned int
0x1800156ea  lea     r8, [rsp+0C8h+var_88]; unsigned int *
0x1800156ef  lea     rdx, aUniqueid; "UniqueId"
0x1800156f6  mov     rcx, [rsp+0C8h+hKey]; HKEY
0x1800156fb  call    ?RegQueryDword@@YAJPEAUHKEY__@@PEAGPEAKK@Z; RegQueryDword(HKEY__ *,ushort *,ulong *,ulong)
0x180015700  mov     esi, eax
0x180015702  test    eax, eax
0x180015704  jns     short loc_180015742
0x180015706  lea     rax, aFailedToOpenUn; "Failed to open UniqueId subkey"
0x18001570d  mov     [rsp+0C8h+lpcchClass], rax
0x180015712  mov     dword ptr [rsp+0C8h+lpClass], esi
0x180015716  lea     rax, aCtraceRegquery; "CTrace::RegQueryComponentTraceContext"
0x18001571d  mov     [rsp+0C8h+phkResult], rax
0x180015722  mov     r9d, 333h
0x180015728  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x18001572f  mov     edx, 1
0x180015734  lea     ecx, [rdx+0Dh]
0x180015737  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001573c  nop
0x18001573d  jmp     loc_18001595C
0x180015742  lea     r8, [rsp+0C8h+var_78]; unsigned int *
0x180015747  lea     rdx, aActive; "Active"
0x18001574e  mov     rcx, [rsp+0C8h+hKey]; HKEY
0x180015753  test    rbx, rbx
0x180015756  jz      short loc_1800157A0
0x180015758  mov     r9d, [rbx]; unsigned int
0x18001575b  call    ?RegQueryDword@@YAJPEAUHKEY__@@PEAGPEAKK@Z; RegQueryDword(HKEY__ *,ushort *,ulong *,ulong)
0x180015760  mov     eax, [rbx]
0x180015762  and     eax, [rsp+0C8h+var_78]
0x180015766  mov     [rsp+0C8h+var_58], eax
0x18001576a  mov     r9d, [rbx+4]; unsigned int
0x18001576e  lea     r8, [rsp+0C8h+var_58+4]; unsigned int *
0x180015773  lea     rdx, aLevel; "Level"
0x18001577a  mov     rcx, [rsp+0C8h+hKey]; HKEY
0x18001577f  call    ?RegQueryDword@@YAJPEAUHKEY__@@PEAGPEAKK@Z; RegQueryDword(HKEY__ *,ushort *,ulong *,ulong)
0x180015784  mov     r9d, [rbx+8]; unsigned int
0x180015788  lea     r8, [rsp+0C8h+var_50]; unsigned int *
0x18001578d  lea     rdx, aControlflags; "ControlFlags"
0x180015794  mov     rcx, [rsp+0C8h+hKey]; HKEY
0x180015799  call    ?RegQueryDword@@YAJPEAUHKEY__@@PEAGPEAKK@Z; RegQueryDword(HKEY__ *,ushort *,ulong *,ulong)
0x18001579e  jmp     short loc_1800157E5
0x1800157a0  mov     r9d, 1; unsigned int
0x1800157a6  call    ?RegQueryDword@@YAJPEAUHKEY__@@PEAGPEAKK@Z; RegQueryDword(HKEY__ *,ushort *,ulong *,ulong)
0x1800157ab  mov     eax, [rsp+0C8h+var_78]
0x1800157af  mov     [rsp+0C8h+var_58], eax
0x1800157b3  xor     r9d, r9d; unsigned int
0x1800157b6  lea     r8, [rsp+0C8h+var_58+4]; unsigned int *
0x1800157bb  lea     rdx, aLevel; "Level"
0x1800157c2  mov     rcx, [rsp+0C8h+hKey]; HKEY
0x1800157c7  call    ?RegQueryDword@@YAJPEAUHKEY__@@PEAGPEAKK@Z; RegQueryDword(HKEY__ *,ushort *,ulong *,ulong)
0x1800157cc  xor     r9d, r9d; unsigned int
0x1800157cf  lea     r8, [rsp+0C8h+var_50]; unsigned int *
0x1800157d4  lea     rdx, aControlflags; "ControlFlags"
0x1800157db  mov     rcx, [rsp+0C8h+hKey]; HKEY
0x1800157e0  call    ?RegQueryDword@@YAJPEAUHKEY__@@PEAGPEAKK@Z; RegQueryDword(HKEY__ *,ushort *,ulong *,ulong)
0x1800157e5  lea     r15, [r12+660h]
0x1800157ed  lea     r8, [rsp+0C8h+var_88]
0x1800157f2  lea     rdx, [rsp+0C8h+var_70]
0x1800157f7  mov     rcx, r15
0x1800157fa  call    ?find@?$_Tree@V?$_Tmap_traits@KPEAU_TRACE_CONTEXT@@U?$less@K@std@@V?$throwing_allocator@PEAU_TRACE_CONTEXT@@@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAU_TRACE_CONTEXT@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,_TRACE_CONTEXT *,std::less<ulong>,throwing_allocator<_TRACE_CONTEXT *>,0>>::find(ulong const &)
0x1800157ff  mov     rcx, [rax]
0x180015802  cmp     rcx, [r15]
0x180015805  jnz     loc_1800158D2
0x18001580b  mov     ecx, 0Ch; Size
0x180015810  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015815  mov     r13, rax
0x180015818  test    rax, rax
0x18001581b  jnz     short loc_18001585D
0x18001581d  mov     esi, 8007000Eh
0x180015822  lea     rax, aNewTraceContex; "new TRACE_CONTEXT Failed"
0x180015829  mov     [rsp+0C8h+lpcchClass], rax
0x18001582e  mov     dword ptr [rsp+0C8h+lpClass], esi
0x180015832  lea     rax, aCtraceRegquery; "CTrace::RegQueryComponentTraceContext"
0x180015839  mov     [rsp+0C8h+phkResult], rax
0x18001583e  mov     r9d, 36Fh
0x180015844  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x18001584b  lea     edx, [r13+1]
0x18001584f  lea     ecx, [rdx+0Dh]
0x180015852  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180015857  nop
0x180015858  jmp     loc_18001595C
0x18001585d  movsd   xmm0, qword ptr [rsp+0C8h+var_58]
0x180015863  movsd   qword ptr [rax], xmm0
0x180015867  mov     eax, [rsp+0C8h+var_50]
0x18001586b  mov     [r13+8], eax
0x18001586f  lea     r8, [rsp+0C8h+var_88]
0x180015874  lea     rdx, [rsp+0C8h+var_70]
0x180015879  mov     rcx, r15
0x18001587c  call    ?lower_bound@?$_Tree@V?$_Tmap_traits@KPEAU_TRACE_CONTEXT@@U?$less@K@std@@V?$throwing_allocator@PEAU_TRACE_CONTEXT@@@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAU_TRACE_CONTEXT@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,_TRACE_CONTEXT *,std::less<ulong>,throwing_allocator<_TRACE_CONTEXT *>,0>>::lower_bound(ulong const &)
0x180015881  mov     rbx, qword ptr [rsp+0C8h+var_70]
0x180015886  mov     eax, [rsp+0C8h+var_88]
0x18001588a  cmp     rbx, [r15]
0x18001588d  jz      short loc_180015894
0x18001588f  cmp     eax, [rbx+20h]
0x180015892  jnb     short loc_1800158CC
0x180015894  mov     [rsp+0C8h+var_70], eax
0x180015898  mov     [rsp+0C8h+var_68], 0
0x1800158a1  lea     rdx, [rsp+0C8h+var_70]
0x1800158a6  mov     rcx, r15
0x1800158a9  call    ??$_Buynode@U?$pair@KPEAU_TRACE_CONTEXT@@@std@@@?$_Tree_buy@U?$pair@$$CBKPEAU_TRACE_CONTEXT@@@std@@V?$throwing_allocator@PEAU_TRACE_CONTEXT@@@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKPEAU_TRACE_CONTEXT@@@std@@PEAX@1@$$QEAU?$pair@KPEAU_TRACE_CONTEXT@@@1@@Z; std::_Tree_buy<std::pair<ulong const,_TRACE_CONTEXT *>,throwing_allocator<_TRACE_CONTEXT *>>::_Buynode<std::pair<ulong,_TRACE_CONTEXT *>>(std::pair<ulong,_TRACE_CONTEXT *> &&)
0x1800158ae  lea     r9, [rax+20h]
0x1800158b2  mov     [rsp+0C8h+phkResult], rax; void *
0x1800158b7  mov     r8, rbx; int
0x1800158ba  lea     rdx, [rsp+0C8h+var_70]; int
0x1800158bf  mov     rcx, r15; int
0x1800158c2  call    ??$_Insert_hint@AEAU?$pair@$$CBKPEAU_TRACE_CONTEXT@@@std@@PEAU?$_Tree_node@U?$pair@$$CBKPEAU_TRACE_CONTEXT@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@KPEAU_TRACE_CONTEXT@@U?$less@K@std@@V?$throwing_allocator@PEAU_TRACE_CONTEXT@@@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAU_TRACE_CONTEXT@@@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAU_TRACE_CONTEXT@@@std@@@std@@@std@@@1@AEAU?$pair@$$CBKPEAU_TRACE_CONTEXT@@@1@PEAU?$_Tree_node@U?$pair@$$CBKPEAU_TRACE_CONTEXT@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<ulong,_TRACE_CONTEXT *,std::less<ulong>,throwing_allocator<_TRACE_CONTEXT *>,0>>::_Insert_hint<std::pair<ulong const,_TRACE_CONTEXT *> &,std::_Tree_node<std::pair<ulong const,_TRACE_CONTEXT *>,void *> *>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,_TRACE_CONTEXT *>>>>,std::pair<ulong const,_TRACE_CONTEXT *> &,std::_Tree_node<std::pair<ulong const,_TRACE_CONTEXT *>,void *> *)
0x1800158c7  mov     rbx, qword ptr [rsp+0C8h+var_70]
0x1800158cc  mov     [rbx+28h], r13
0x1800158d0  jmp     short loc_1800158E7
0x1800158d2  mov     rcx, [rcx+28h]
0x1800158d6  movsd   xmm0, qword ptr [rsp+0C8h+var_58]
0x1800158dc  movsd   qword ptr [rcx], xmm0
0x1800158e0  mov     eax, [rsp+0C8h+var_50]
0x1800158e4  mov     [rcx+8], eax
0x1800158e7  xor     ebx, ebx
0x1800158e9  mov     [rsp+0C8h+cchName], 304h
0x1800158f1  mov     [rsp+0C8h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800158fa  mov     [rsp+0C8h+lpcchClass], 0; lpcchClass
0x180015903  mov     [rsp+0C8h+lpClass], 0; lpClass
0x18001590c  mov     [rsp+0C8h+phkResult], 0; lpReserved
0x180015915  lea     r9, [rsp+0C8h+cchName]; lpcchName
0x18001591a  mov     r8, r14; lpName
0x18001591d  mov     edx, ebx; dwIndex
0x18001591f  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180015924  call    cs:__imp_RegEnumKeyExW
0x18001592a  mov     r15d, eax
0x18001592d  test    eax, eax
0x18001592f  jnz     short loc_180015946
0x180015931  lea     r9, [rsp+0C8h+var_58]; struct _TRACE_CONTEXT *
0x180015936  mov     r8, r14; unsigned __int16 *
0x180015939  mov     rdx, [rsp+0C8h+hKey]; HKEY
0x18001593e  mov     rcx, r12; this
0x180015941  call    ?RegQueryComponentTraceContext@CTrace@@AEAAJPEAUHKEY__@@PEAGPEAU_TRACE_CONTEXT@@@Z; CTrace::RegQueryComponentTraceContext(HKEY__ *,ushort *,_TRACE_CONTEXT *)
0x180015946  inc     ebx
0x180015948  cmp     r15d, 103h
0x18001594f  jnz     short loc_1800158E9
0x180015951  jmp     short loc_18001595C
0x180015953  mov     esi, [rsp+0C8h+var_70]
0x180015957  mov     r14, [rsp+0C8h+var_60]
0x18001595c  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180015961  test    rcx, rcx
0x180015964  jz      short loc_18001596C
0x180015966  call    cs:__imp_RegCloseKey
0x18001596c  test    r14, r14
0x18001596f  jz      short loc_180015979
0x180015971  mov     rcx, r14; Block
0x180015974  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015979  mov     eax, esi
0x18001597b  mov     rcx, [rsp+0C8h+var_48]
0x180015983  xor     rcx, rsp; StackCookie
0x180015986  call    __security_check_cookie
0x18001598b  add     rsp, 98h
0x180015992  pop     r15
0x180015994  pop     r14
0x180015996  pop     r13
0x180015998  pop     r12
0x18001599a  pop     rsi
0x18001599b  pop     rbx
0x18001599c  retn
```
