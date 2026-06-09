# AccessibilityCplCore::SetupQuestions(ushort const *)

- ea: `0x180019740`
- end: `0x1800198eb`
- name: `?SetupQuestions@AccessibilityCplCore@@AEAAXPEBG@Z`
- size: `427`
- prototype: `void(AccessibilityCplCore *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180007a70`

## callees

- `0x1800055c0`
- `0x1800057d4`
- `0x180014b34`
- `0x180019740`
- `0x18001a6c0`
- `0x18002d220`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019899`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019899`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800198a6`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800198a6`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180019851`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180019851`
- `DUI70!?SetNotifyHandler@CCBase@DirectUI@@QEAAXP6AHI_K_JPEA_JPEAX@Z3@Z` at `0x1800198b9`
- `DUI70!?SetNotifyHandler@CCBase@DirectUI@@QEAAXP6AHI_K_JPEA_JPEAX@Z3@Z` at `0x1800198b9`
- `DUI70!StrToID` at `0x18001982c`
- `DUI70!StrToID` at `0x180019869`
- `DUI70!StrToID` at `0x18001982c`
- `DUI70!StrToID` at `0x180019869`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019838`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019875`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019838`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019875`

## string_xrefs

- `0x18001979c`: `Software\Microsoft\Ease of Access`

## pseudocode

```c
void __fastcall AccessibilityCplCore::SetupQuestions(
        AccessibilityCplCore *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  __int64 v6; // rdi
  DirectUI::Element *v7; // rbx
  unsigned __int16 v8; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v10; // rbx
  unsigned __int16 v11; // ax
  DirectUI::Element *v12; // rbx
  HKEY v13; // [rsp+30h] [rbp-D0h]
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v15[6]; // [rsp+48h] [rbp-B8h]
  _QWORD v16[3]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v17[12]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Buffer[512]; // [rsp+90h] [rbp-70h] BYREF

  memset(v16, 0, sizeof(v16));
  if ( !(unsigned int)ATL::CRegKey::Create(
                        (ATL::CRegKey *)v16,
                        HKEY_CURRENT_USER,
                        L"Software\\Microsoft\\Ease of Access",
                        a4,
                        0,
                        1u,
                        v13,
                        0) )
  {
    v14 = 0;
    ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v16, a2, &v14);
    v6 = 0;
    v15[0] = 1;
    v15[1] = 2;
    v15[2] = 4;
    v15[3] = 8;
    v15[4] = 16;
    v15[5] = 32;
    do
    {
      StringCchPrintfW(v17, 0xAu, L"q%d", (unsigned int)v6);
      v7 = (DirectUI::Element *)*((_QWORD *)this + 12);
      v8 = StrToID(v17);
      Descendent = DirectUI::Element::FindDescendent(v7, v8);
      if ( Descendent )
        DirectUI::Element::SetSelected(Descendent, (v15[v6] & v14) != 0);
      v6 = (unsigned int)(v6 + 1);
    }
    while ( (unsigned int)v6 < 6 );
    v10 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v11 = StrToID(L"privacy");
    v12 = DirectUI::Element::FindDescendent(v10, v11);
    if ( v12 )
    {
      LoadStringW(g_hinst, 4u, Buffer, 512);
      DirectUI::Element::SetContentString(v12, Buffer);
      DirectUI::CCBase::SetNotifyHandler(
        v12,
        (int (*)(unsigned int, unsigned __int64, __int64, __int64 *, void *))AccessibilityCplCore::CCSysLinkNotifyHandler,
        0);
    }
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v16);
}

```

## disassembly

```asm
0x180019740  mov     [rsp-8+arg_10], rbx
0x180019745  push    rbp
0x180019746  push    rsi
0x180019747  push    rdi
0x180019748  lea     rbp, [rsp-3A0h]
0x180019750  sub     rsp, 4A0h
0x180019757  mov     rax, cs:__security_cookie
0x18001975e  xor     rax, rsp
0x180019761  mov     [rbp+3B0h+var_20], rax
0x180019768  mov     rbx, rdx
0x18001976b  mov     [rsp+4B0h+var_478], 0; unsigned int *
0x180019774  mov     rsi, rcx
0x180019777  mov     [rsp+4B0h+var_488], 1; REGSAM
0x18001977f  mov     rdx, 0FFFFFFFF80000001h; hKey
0x180019786  mov     [rsp+4B0h+var_490], 0; DWORD
0x18001978e  lea     rcx, [rsp+4B0h+var_450]; this
0x180019793  mov     [rsp+4B0h+var_450], 0
0x18001979c  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Ease of Access"
0x1800197a3  mov     [rsp+4B0h+var_448], 0
0x1800197ac  mov     [rsp+4B0h+var_440], 0
0x1800197b5  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1800197ba  test    eax, eax
0x1800197bc  jnz     loc_1800198BF
0x1800197c2  lea     r8, [rsp+4B0h+var_470]; unsigned int *
0x1800197c7  mov     [rsp+4B0h+var_470], eax
0x1800197cb  mov     rdx, rbx; unsigned __int16 *
0x1800197ce  lea     rcx, [rsp+4B0h+var_450]; this
0x1800197d3  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x1800197d8  xor     edi, edi
0x1800197da  mov     [rsp+4B0h+var_468], 1
0x1800197e2  mov     [rsp+4B0h+var_464], 2
0x1800197ea  mov     [rsp+4B0h+var_460], 4
0x1800197f2  mov     [rsp+4B0h+var_45C], 8
0x1800197fa  mov     [rsp+4B0h+var_458], 10h
0x180019802  mov     [rsp+4B0h+var_454], 20h ; ' '
0x18001980a  mov     r9d, edi
0x18001980d  lea     r8, aQD; "q%d"
0x180019814  mov     edx, 0Ah; unsigned __int64
0x180019819  lea     rcx, [rsp+4B0h+var_438]; unsigned __int16 *
0x18001981e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019823  mov     rbx, [rsi+60h]
0x180019827  lea     rcx, [rsp+4B0h+var_438]
0x18001982c  call    cs:__imp_StrToID
0x180019832  movzx   edx, ax
0x180019835  mov     rcx, rbx
0x180019838  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001983e  test    rax, rax
0x180019841  jz      short loc_180019857
0x180019843  mov     edx, [rsp+rdi*4+4B0h+var_468]
0x180019847  mov     rcx, rax
0x18001984a  test    [rsp+4B0h+var_470], edx
0x18001984e  setnz   dl
0x180019851  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x180019857  inc     edi
0x180019859  cmp     edi, 6
0x18001985c  jb      short loc_18001980A
0x18001985e  mov     rbx, [rsi+60h]
0x180019862  lea     rcx, aPrivacy; "privacy"
0x180019869  call    cs:__imp_StrToID
0x18001986f  movzx   edx, ax
0x180019872  mov     rcx, rbx
0x180019875  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001987b  mov     rbx, rax
0x18001987e  test    rax, rax
0x180019881  jz      short loc_1800198BF
0x180019883  mov     rcx, cs:g_hinst; hInstance
0x18001988a  lea     r8, [rbp+3B0h+Buffer]; lpBuffer
0x18001988e  mov     r9d, 200h; cchBufferMax
0x180019894  mov     edx, 4; uID
0x180019899  call    cs:__imp_LoadStringW
0x18001989f  lea     rdx, [rbp+3B0h+Buffer]
0x1800198a3  mov     rcx, rbx
0x1800198a6  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1800198ac  xor     r8d, r8d
0x1800198af  lea     rdx, ?CCSysLinkNotifyHandler@AccessibilityCplCore@@CAHI_K_JPEA_JPEAX@Z; AccessibilityCplCore::CCSysLinkNotifyHandler(uint,unsigned __int64,__int64,__int64 *,void *)
0x1800198b6  mov     rcx, rbx
0x1800198b9  call    cs:__imp_?SetNotifyHandler@CCBase@DirectUI@@QEAAXP6AHI_K_JPEA_JPEAX@Z3@Z; DirectUI::CCBase::SetNotifyHandler(int (*)(uint,unsigned __int64,__int64,__int64 *,void *),void *)
0x1800198bf  lea     rcx, [rsp+4B0h+var_450]; this
0x1800198c4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800198c9  mov     rcx, [rbp+3B0h+var_20]
0x1800198d0  xor     rcx, rsp; StackCookie
0x1800198d3  call    __security_check_cookie
0x1800198d8  mov     rbx, [rsp+4B0h+arg_10]
0x1800198e0  add     rsp, 4A0h
0x1800198e7  pop     rdi
0x1800198e8  pop     rsi
0x1800198e9  pop     rbp
0x1800198ea  retn
```
