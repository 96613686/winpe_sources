# GetInterfaceHelperClsid(_GUID const &,_GUID *,int *)

- ea: `0x180015464`
- end: `0x180015804`
- name: `?GetInterfaceHelperClsid@@YAJAEBU_GUID@@PEAU1@PEAH@Z`
- size: `928`
- prototype: `HRESULT __fastcall(const _GUID *iid, _GUID *pClsid, int *pfDisableTypelib)`
- caller_count: `2`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800144e8`
- `0x180014f80`

## callees

- `0x180013bec`
- `0x180013c20`
- `0x180014090`
- `0x180015464`
- `0x180016028`
- `0x180016744`
- `0x1800167d8`
- `0x180017894`
- `0x180018a34`
- `0x180018b30`
- `0x18004197c`
- `0x180052390`
- `0x1800c4645`
- `0x1800ce010`

## import_xrefs

- `ntdll!ZwClose` at `0x18001576a`
- `ntdll!ZwClose` at `0x18001576a`
- `ntdll!RtlInitUnicodeString` at `0x1800156c7`
- `ntdll!RtlInitUnicodeString` at `0x1800156c7`
- `ntdll!ZwOpenKey` at `0x180015703`
- `ntdll!ZwOpenKey` at `0x180015703`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015617`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015617`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015775`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800157f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015775`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800157f4`

## string_xrefs

- `0x18001565c`: `\Registry\Machine\Software\Classes\`

## pseudocode

```c
__int64 __fastcall GetInterfaceHelperClsid(__m128i *iid, _GUID *pClsid, int *pfDisableTypelib)
{
  CALLFRAME_CACHE<INTERFACE_HELPER_CLSID> *v3; // rdi
  int v7; // eax
  Map<MAP_KEY_GUID,INTERFACE_HELPER_CLSID *,MAP_HASHER<MAP_KEY_GUID>,AllocateThrow>::Assoc **i; // rbx
  Map<MAP_KEY_GUID,INTERFACE_HELPER_CLSID *,MAP_HASHER<MAP_KEY_GUID>,AllocateThrow>::Assoc *v9; // rbx
  INTERFACE_HELPER_CLSID *m_r; // rbx
  int v11; // esi
  unsigned int RegistryValue; // edi
  CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID> *v13; // rcx
  __int64 result; // rax
  __int64 v15; // r8
  const wchar_t *v16; // rdx
  __int64 v17; // rax
  wchar_t *v18; // rcx
  wchar_t *v19; // rdx
  HANDLE v20; // rcx
  char *v21; // rax
  _GUID *v22; // rsi
  NTSTATUS v23; // eax
  unsigned int v24; // r9d
  CALLFRAME_CACHE<INTERFACE_HELPER_CLSID> *v25; // rdx
  void *v26; // rbx
  HRESULT v27; // eax
  HREG hkey; // [rsp+20h] [rbp-B9h] BYREF
  wchar_t *wszFullKeyName; // [rsp+28h] [rbp-B1h] BYREF
  __m128i pinfo; // [rsp+30h] [rbp-A9h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-99h] BYREF
  wchar_t wszKey[64]; // [rsp+70h] [rbp-69h] BYREF

  v3 = g_pihCache;
  if ( g_pihCache->m_fCsInitialized )
    XSLOCK::LockShared(&g_pihCache->m_lock, (int)pClsid);
  v7 = _mm_cvtsi128_si32(*iid);
  pinfo = *iid;
  for ( i = &v3->m_map.m_rgpAssoc[(214013 * v7 + 2531011) % v3->m_map.m_cAssoc]; ; i = &v9->m_pAssocNext )
  {
    v9 = *i;
    if ( !v9 )
      break;
    if ( !memcmp_0(&v9->m_d, &pinfo, 0x10u) )
    {
      m_r = v9->m_r;
      v11 = 0;
      _InterlockedIncrement(&m_r->m_refs);
      m_r->m_dwReleaseTime = -1;
      goto LABEL_8;
    }
  }
  m_r = 0;
  v11 = -2147467262;
LABEL_8:
  if ( v3->m_fCsInitialized )
    XSLOCK::ReleaseLock(&v3->m_lock);
  if ( !v11 )
  {
    *pfDisableTypelib = m_r->m_fDisableTypeLib;
    if ( m_r->m_fDisableAll )
    {
      RegistryValue = -2147023838;
    }
    else if ( m_r->m_fFoundHelper )
    {
      RegistryValue = 0;
      *pClsid = m_r->m_clsid;
    }
    else
    {
      RegistryValue = -2147024894;
    }
    v13 = m_r;
    goto LABEL_15;
  }
  v15 = 59;
  v16 = L"Interface\\";
  v17 = 2147483646;
  v18 = wszKey;
  do
  {
    if ( !v17 )
      break;
    if ( !*v16 )
      break;
    *v18++ = *v16++;
    --v17;
    --v15;
  }
  while ( v15 );
  v19 = v18 - 1;
  result = v15 == 0 ? 0x8007007A : 0;
  if ( v15 )
    v19 = v18;
  *v19 = 0;
  if ( v15 )
  {
    StringFromGuid((const _GUID *)iid, &wszKey[10]);
    v20 = g_hHeap;
    hkey.h = 0;
    wszFullKeyName = 0;
    *pfDisableTypelib = 0;
    v21 = (char *)HeapAlloc(v20, 0, 0x50u);
    v22 = (_GUID *)v21;
    if ( !v21 )
      return (unsigned int)-2147024882;
    *((_DWORD *)v21 + 2) = -1;
    *(_QWORD *)v21 = CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID>::`vftable';
    *((_DWORD *)v21 + 6) = 1;
    *((_QWORD *)v21 + 2) = 0;
    *(_QWORD *)v21 = INTERFACE_HELPER_CLSID::`vftable';
    *(GUID *)(v21 + 28) = GUID_NULL;
    *((_QWORD *)v21 + 8) = 0;
    *((_DWORD *)v21 + 18) = 0;
    *((GUID *)v21 + 3) = GUID_NULL;
    *(__m128i *)(v21 + 28) = *iid;
    RegistryValue = StringCat(&wszFullKeyName, L"\\Registry\\Machine\\Software\\Classes\\", wszKey, 0);
    if ( RegistryValue )
      goto LABEL_39;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    pinfo = 0;
    RtlInitUnicodeString((PUNICODE_STRING)&pinfo, wszFullKeyName);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (_UNICODE_STRING *)&pinfo;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v23 = ZwOpenKey(&hkey.h, 0x20019u, &ObjectAttributes);
    RegistryValue = HrNt(v23);
    if ( !RegistryValue )
    {
      if ( FDisableAssociatedInterceptor(hkey, L"InterfaceHelperDisableTypeLib") )
      {
        *pfDisableTypelib = 1;
        v22[4].Data1 = 1;
      }
      if ( FDisableAssociatedInterceptor(hkey, L"InterfaceHelperDisableAll") )
      {
        RegistryValue = -2147023838;
        *(_DWORD *)&v22[4].Data2 = 1;
      }
      else
      {
        pinfo.m128i_i64[0] = 0;
        RegistryValue = GetRegistryValue(hkey, L"InterfaceHelperUser", (_KEY_VALUE_FULL_INFORMATION **)&pinfo, v24);
        if ( !RegistryValue )
        {
          v26 = (void *)pinfo.m128i_i64[0];
          v27 = GuidFromString(
                  (const wchar_t *)(pinfo.m128i_i64[0] + *(unsigned int *)(pinfo.m128i_i64[0] + 8)),
                  pClsid);
          *(_DWORD *)v22[4].Data4 = 1;
          RegistryValue = v27;
          v22[3] = *pClsid;
          CoTaskMemFree(v26);
        }
      }
      ZwClose(hkey.h);
    }
    CoTaskMemFree(wszFullKeyName);
    if ( CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID>::AddToCache(
           (CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID> *)v22,
           v25) < 0 )
    {
LABEL_39:
      (**(void (__fastcall ***)(char *, __int64))&v22->Data1)((char *)v22, 1);
      return RegistryValue;
    }
    v13 = (CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID> *)v22;
LABEL_15:
    CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID>::Release(v13, 1);
    return RegistryValue;
  }
  return result;
}

```

## disassembly

```asm
0x180015464  mov     [rsp-8+arg_18], rbx
0x180015469  push    rbp
0x18001546a  push    rsi
0x18001546b  push    rdi
0x18001546c  push    r12
0x18001546e  push    r13
0x180015470  push    r14
0x180015472  push    r15
0x180015474  lea     rbp, [rsp-27h]
0x180015479  sub     rsp, 100h
0x180015480  mov     rax, cs:__security_cookie
0x180015487  xor     rax, rsp
0x18001548a  mov     [rbp+57h+var_40], rax
0x18001548e  mov     rdi, cs:?g_pihCache@@3PEAV?$CALLFRAME_CACHE@UINTERFACE_HELPER_CLSID@@@@EA; CALLFRAME_CACHE<INTERFACE_HELPER_CLSID> * g_pihCache
0x180015495  xor     r13d, r13d
0x180015498  mov     r14, pfDisableTypelib
0x18001549b  mov     r15, pClsid
0x18001549e  mov     r12, iid
0x1800154a1  cmp     [rdi+0A0h], r13d
0x1800154a8  jz      short loc_1800154B3
0x1800154aa  lea     iid, [rdi+8]; this
0x1800154ae  call    ?LockShared@XSLOCK@@QEAAHH@Z; XSLOCK::LockShared(int)
0x1800154b3  movups  xmm0, xmmword ptr [r12]
0x1800154b8  xor     edx, edx
0x1800154ba  movd    eax, xmm0
0x1800154be  movups  [rsp+130h+pinfo], xmm0
0x1800154c3  imul    eax, 343FDh
0x1800154c9  add     eax, 269EC3h
0x1800154ce  div     dword ptr [rdi+80h]
0x1800154d4  mov     rax, [rdi+78h]
0x1800154d8  lea     rbx, [rax+pClsid*8]
0x1800154dc  mov     rbx, [rbx]
0x1800154df  test    rbx, rbx
0x1800154e2  jz      loc_180015586
0x1800154e8  lea     iid, [rbx+1Ch]; Buf1
0x1800154ec  mov     r8d, 10h; Size
0x1800154f2  lea     pClsid, [rsp+130h+pinfo]; Buf2
0x1800154f7  call    memcmp_0
0x1800154fc  test    eax, eax
0x1800154fe  jz      short loc_180015506
0x180015500  add     rbx, 10h
0x180015504  jmp     short loc_1800154DC
0x180015506  mov     rbx, [rbx+30h]
0x18001550a  mov     esi, r13d
0x18001550d  lock inc dword ptr [rbx+18h]
0x180015511  mov     eax, [rbx+18h]
0x180015514  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x18001551b  cmp     [rdi+0A0h], r13d
0x180015522  jz      short loc_18001552D
0x180015524  lea     iid, [rdi+8]; this
0x180015528  call    ?ReleaseLock@XSLOCK@@QEAAXXZ; XSLOCK::ReleaseLock(void)
0x18001552d  test    esi, esi
0x18001552f  jnz     short loc_180015590
0x180015531  mov     eax, [rbx+40h]
0x180015534  mov     [r14], eax
0x180015537  cmp     [rbx+44h], r13d
0x18001553b  jnz     loc_18001562F
0x180015541  cmp     [rbx+48h], r13d
0x180015545  jnz     loc_1800157A6
0x18001554b  mov     edi, 80070002h
0x180015550  mov     edx, 1; bAgeOutOldEntries
0x180015555  mov     iid, rbx; this
0x180015558  call    ?Release@?$CALLFRAME_CACHE_ENTRY@UINTERFACE_HELPER_CLSID@@@@QEAAKH@Z; CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID>::Release(int)
0x18001555d  mov     eax, edi
0x18001555f  mov     iid, [rbp+57h+var_40]
0x180015563  xor     iid, rsp; StackCookie
0x180015566  call    __security_check_cookie
0x18001556b  mov     rbx, [rsp+130h+arg_18]
0x180015573  add     rsp, 100h
0x18001557a  pop     r15
0x18001557c  pop     r14
0x18001557e  pop     r13
0x180015580  pop     r12
0x180015582  pop     rdi
0x180015583  pop     rsi
0x180015584  pop     rbp
0x180015585  retn
0x180015586  mov     rbx, r13
0x180015589  mov     esi, 80004002h
0x18001558e  jmp     short loc_18001551B
0x180015590  mov     r8d, 3Bh ; ';'
0x180015596  lea     pClsid, aInterface; "Interface\\"
0x18001559d  mov     eax, 7FFFFFFEh
0x1800155a2  lea     iid, [rbp+57h+wszKey]
0x1800155a6  lea     ebx, [pfDisableTypelib-3Ah]
0x1800155aa  test    rax, rax
0x1800155ad  jz      short loc_1800155CD
0x1800155af  movzx   r9d, word ptr [pClsid]
0x1800155b3  test    r9w, r9w
0x1800155b7  jz      short loc_1800155CD
0x1800155b9  mov     [iid], r9w
0x1800155bd  add     pClsid, 2
0x1800155c1  add     iid, 2
0x1800155c5  sub     rax, rbx
0x1800155c8  sub     pfDisableTypelib, rbx
0x1800155cb  jnz     short loc_1800155AA
0x1800155cd  mov     rax, pfDisableTypelib
0x1800155d0  lea     pClsid, [iid-2]
0x1800155d4  neg     rax
0x1800155d7  sbb     eax, eax
0x1800155d9  not     eax
0x1800155db  and     eax, 8007007Ah
0x1800155e0  test    pfDisableTypelib, pfDisableTypelib
0x1800155e3  cmovnz  pClsid, iid
0x1800155e7  mov     [pClsid], r13w
0x1800155eb  jz      loc_18001555F
0x1800155f1  lea     pClsid, [rbp+57h+wszKey+14h]; pwsz
0x1800155f5  mov     iid, r12; guid
0x1800155f8  call    ?StringFromGuid@@YAXAEBU_GUID@@PEAG@Z; StringFromGuid(_GUID const &,ushort *)
0x1800155fd  mov     iid, cs:?g_hHeap@@3QEAXEA; hHeap
0x180015604  xor     edx, edx; dwFlags
0x180015606  mov     [rsp+130h+hkey.h], r13
0x18001560b  mov     [rsp+130h+wszFullKeyName], r13
0x180015610  mov     [r14], r13d
0x180015613  lea     r8d, [pClsid+50h]; dwBytes
0x180015617  call    cs:__imp_HeapAlloc
0x18001561d  mov     rsi, rax
0x180015620  test    rax, rax
0x180015623  jnz     short loc_180015639
0x180015625  mov     edi, 8007000Eh
0x18001562a  jmp     loc_18001555D
0x18001562f  mov     edi, 80070422h
0x180015634  jmp     loc_180015550
0x180015639  mov     dword ptr [rsi+8], 0FFFFFFFFh
0x180015640  lea     rax, ??_7?$CALLFRAME_CACHE_ENTRY@UINTERFACE_HELPER_CLSID@@@@6B@; const CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID>::`vftable'
0x180015647  mov     [rsi], rax
0x18001564a  lea     pfDisableTypelib, [rbp+57h+wszKey]
0x18001564e  mov     [rsi+18h], ebx
0x180015651  lea     rax, ??_7INTERFACE_HELPER_CLSID@@6B@; const INTERFACE_HELPER_CLSID::`vftable'
0x180015658  mov     [rsi+10h], r13
0x18001565c  lea     pClsid, aRegistryMachin_1; "\\Registry\\Machine\\Software\\Classes"...
0x180015663  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001566a  mov     [rsi], rax
0x18001566d  lea     iid, [rsp+130h+wszFullKeyName]; pwsz
0x180015672  xor     r9d, r9d
0x180015675  movdqu  xmmword ptr [rsi+1Ch], xmm0
0x18001567a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180015681  mov     [rsi+40h], r13
0x180015685  mov     [rsi+48h], r13d
0x180015689  movdqu  xmmword ptr [rsi+30h], xmm0
0x18001568e  movups  xmm0, xmmword ptr [r12]
0x180015693  movdqu  xmmword ptr [rsi+1Ch], xmm0
0x180015698  call    ?StringCat@@YAJPEAPEAGZZ; StringCat(ushort * *,...)
0x18001569d  mov     edi, eax
0x18001569f  test    eax, eax
0x1800156a1  jnz     loc_180015791
0x1800156a7  mov     pClsid, [rsp+130h+wszFullKeyName]; SourceString
0x1800156ac  lea     iid, [rsp+130h+pinfo]; DestinationString
0x1800156b1  xorps   xmm0, xmm0
0x1800156b4  movups  xmmword ptr [rsp+130h+ObjectAttributes.Length], xmm0
0x1800156b9  movups  xmmword ptr [rsp+130h+ObjectAttributes.ObjectName], xmm0
0x1800156be  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800156c2  movups  [rsp+130h+pinfo], xmm0
0x1800156c7  call    cs:__imp_RtlInitUnicodeString
0x1800156cd  lea     rax, [rsp+130h+pinfo]
0x1800156d2  mov     [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x1800156da  xorps   xmm0, xmm0
0x1800156dd  mov     [rsp+130h+ObjectAttributes.ObjectName], rax
0x1800156e2  lea     pfDisableTypelib, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x1800156e7  mov     [rsp+130h+ObjectAttributes.RootDirectory], r13
0x1800156ec  mov     edx, 20019h; DesiredAccess
0x1800156f1  mov     [rsp+130h+ObjectAttributes.Attributes], 40h ; '@'
0x1800156f9  lea     iid, [rsp+130h+hkey]; KeyHandle
0x1800156fe  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180015703  call    cs:__imp_ZwOpenKey
0x180015709  mov     ecx, eax; status
0x18001570b  call    HrNt
0x180015710  mov     edi, eax
0x180015712  test    eax, eax
0x180015714  jnz     short loc_180015770
0x180015716  mov     iid, [rsp+130h+hkey.h]; hkey
0x18001571b  lea     pClsid, aInterfacehelpe; "InterfaceHelperDisableTypeLib"
0x180015722  call    ?FDisableAssociatedInterceptor@@YAHUHREG@@PEBG@Z; FDisableAssociatedInterceptor(HREG,ushort const *)
0x180015727  test    eax, eax
0x180015729  jnz     loc_1800157B7
0x18001572f  mov     iid, [rsp+130h+hkey.h]; hkey
0x180015734  lea     pClsid, aInterfacehelpe_1; "InterfaceHelperDisableAll"
0x18001573b  call    ?FDisableAssociatedInterceptor@@YAHUHREG@@PEBG@Z; FDisableAssociatedInterceptor(HREG,ushort const *)
0x180015740  test    eax, eax
0x180015742  jnz     short loc_1800157C2
0x180015744  mov     iid, [rsp+130h+hkey.h]; hkey
0x180015749  lea     pfDisableTypelib, [rsp+130h+pinfo]; ppinfo
0x18001574e  lea     pClsid, aInterfacehelpe_2; "InterfaceHelperUser"
0x180015755  mov     qword ptr [rsp+130h+pinfo], r13
0x18001575a  call    GetRegistryValue
0x18001575f  mov     edi, eax
0x180015761  test    eax, eax
0x180015763  jz      short loc_1800157CC
0x180015765  mov     iid, [rsp+130h+hkey.h]; Handle
0x18001576a  call    cs:__imp_ZwClose
0x180015770  mov     iid, [rsp+130h+wszFullKeyName]; pv
0x180015775  call    cs:__imp_CoTaskMemFree
0x18001577b  mov     iid, rsi; this
0x18001577e  call    ?AddToCache@?$CALLFRAME_CACHE_ENTRY@UINTERFACE_HELPER_CLSID@@@@QEAAJPEAV?$CALLFRAME_CACHE@UINTERFACE_HELPER_CLSID@@@@@Z; CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID>::AddToCache(CALLFRAME_CACHE<INTERFACE_HELPER_CLSID> *)
0x180015783  test    eax, eax
0x180015785  js      short loc_180015791
0x180015787  mov     edx, ebx
0x180015789  mov     iid, rsi
0x18001578c  jmp     loc_180015558
0x180015791  mov     rax, [rsi]
0x180015794  mov     edx, ebx
0x180015796  mov     iid, rsi
0x180015799  mov     rax, [rax]
0x18001579c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157a1  jmp     loc_18001555D
0x1800157a6  movups  xmm0, xmmword ptr [rbx+30h]
0x1800157aa  mov     edi, r13d
0x1800157ad  movdqu  xmmword ptr [r15], xmm0
0x1800157b2  jmp     loc_180015550
0x1800157b7  mov     [r14], ebx
0x1800157ba  mov     [rsi+40h], ebx
0x1800157bd  jmp     loc_18001572F
0x1800157c2  mov     edi, 80070422h
0x1800157c7  mov     [rsi+44h], ebx
0x1800157ca  jmp     short loc_180015765
0x1800157cc  mov     rbx, qword ptr [rsp+130h+pinfo]
0x1800157d1  mov     pClsid, r15; pguid
0x1800157d4  mov     ecx, [rbx+8]
0x1800157d7  add     iid, rbx; lpsz
0x1800157da  call    ?GuidFromString@@YAJPEBGPEAU_GUID@@@Z; GuidFromString(ushort const *,_GUID *)
0x1800157df  mov     dword ptr [rsi+48h], 1
0x1800157e6  mov     iid, rbx; pv
0x1800157e9  movups  xmm0, xmmword ptr [r15]
0x1800157ed  mov     edi, eax
0x1800157ef  movdqu  xmmword ptr [rsi+30h], xmm0
0x1800157f4  call    cs:__imp_CoTaskMemFree
0x1800157fa  mov     ebx, 1
0x1800157ff  jmp     loc_180015765
```
