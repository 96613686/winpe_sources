# CMidiClientManager::OnDeviceRemoved(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x14001bf60`
- end: `0x14001c388`
- name: `?OnDeviceRemoved@CMidiClientManager@@QEAAXAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1064`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14002ddf0`

## callees

- `0x14000179c`
- `0x140001ce8`
- `0x140002184`
- `0x1400054c0`
- `0x140007c20`
- `0x14000984c`
- `0x140013a38`
- `0x14001ba58`
- `0x14001bf60`
- `0x14001f95c`

## string_xrefs

- `0x14001bf9b`: `CMidiClientManager::OnDeviceRemoved`
- `0x14001c0db`: `CMidiClientManager::OnDeviceRemoved`
- `0x14001c25f`: `CMidiClientManager::OnDeviceRemoved`
- `0x14001c32a`: `CMidiClientManager::OnDeviceRemoved`

## pseudocode

```c
__int64 __fastcall CMidiClientManager::OnDeviceRemoved(__int64 a1, const wchar_t **a2)
{
  int v3; // r14d
  _DWORD *v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  _DWORD *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rbx
  const wchar_t *v12; // rdi
  const wchar_t *v13; // r15
  _QWORD *v14; // rsi
  _DWORD *v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  const wchar_t *v18; // rax
  const wchar_t *v19; // rdx
  const wchar_t *v20; // rcx
  wchar_t *v21; // r8
  bool v22; // r14
  __int64 **v23; // rcx
  __int64 *i; // rax
  _DWORD *v25; // r14
  const wchar_t *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  __int64 *j; // rcx
  unsigned int *v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 result; // rax
  int v36; // [rsp+40h] [rbp-C0h]
  int v37; // [rsp+44h] [rbp-BCh]
  const char *v38; // [rsp+48h] [rbp-B8h] BYREF
  const char *v39; // [rsp+50h] [rbp-B0h] BYREF
  const char *v40; // [rsp+58h] [rbp-A8h] BYREF
  const char *v41; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *S1[3]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v43; // [rsp+80h] [rbp-80h]
  struct _EVENT_DATA_DESCRIPTOR v44; // [rsp+90h] [rbp-70h] BYREF
  const char *v45; // [rsp+B0h] [rbp-50h]
  __int64 v46; // [rsp+B8h] [rbp-48h]
  const wchar_t *v47; // [rsp+C0h] [rbp-40h]
  __int64 v48; // [rsp+C8h] [rbp-38h]
  const wchar_t *v49; // [rsp+D0h] [rbp-30h]
  int v50; // [rsp+D8h] [rbp-28h]
  int v51; // [rsp+DCh] [rbp-24h]
  const wchar_t *v52; // [rsp+E0h] [rbp-20h]
  int v53; // [rsp+E8h] [rbp-18h]
  int v54; // [rsp+ECh] [rbp-14h]

  v3 = 0;
  v5 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v5 > 4u )
  {
    v40 = (const char *)L"Enter";
    v38 = (const char *)a1;
    v39 = "CMidiClientManager::OnDeviceRemoved";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)v5,
      (__int64)&word_14008805E,
      v6,
      v7,
      &v39,
      (__int64)&v38,
      &v40);
  }
  v8 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v8 > 4u )
  {
    v39 = (const char *)L"Acquired client manager lock";
    v38 = (const char *)a1;
    v40 = "CMidiClientManager::OnDeviceRemoved";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)v8,
      (__int64)byte_14008768D,
      v9,
      v10,
      &v40,
      (__int64)&v38,
      &v39);
  }
  v36 = 0;
  v11 = **(__int64 ***)(a1 + 88);
  while ( !*((_BYTE *)v11 + 25) )
  {
    v12 = *a2;
    v13 = a2[1];
    if ( *a2 != v13 )
    {
      while ( 1 )
      {
        v14 = v12 + 12;
        v15 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
        if ( *v15 > 4u )
        {
          if ( *v14 <= 7u )
            v18 = v12;
          else
            v18 = *(const wchar_t **)v12;
          v39 = (const char *)v18;
          v40 = (const char *)a1;
          v38 = (const char *)L"Checking for device pipe with interface id";
          v41 = "CMidiClientManager::OnDeviceRemoved";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            (__int64)v15,
            (__int64)byte_140088251,
            v16,
            v17,
            &v41,
            (__int64)&v40,
            &v38,
            &v39);
        }
        std::wstring::wstring((__int64)S1, v11[8] + 16);
        v37 = v3 | 1;
        if ( *v14 <= 7u )
          v19 = v12;
        else
          v19 = *(const wchar_t **)v12;
        v20 = (const wchar_t *)S1;
        v21 = (wchar_t *)*((_QWORD *)v12 + 2);
        if ( v43 > 7 )
          v20 = S1[0];
        v22 = S1[2] >= v21 && wmemcmp(v20, v19, (size_t)v21) == 0;
        std::wstring::~wstring((char **)S1);
        if ( v22 )
          break;
        v3 = v37;
        v12 += 16;
        if ( v12 == v13 )
          goto LABEL_23;
      }
      v25 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v25 > 4u )
      {
        if ( *v14 > 7u )
          v12 = *(const wchar_t **)v12;
        std::wstring::wstring((__int64)S1, v11[8] + 16);
        v26 = (const wchar_t *)S1;
        v37 |= 2u;
        if ( v43 > 7 )
          v26 = S1[0];
        if ( v12 )
        {
          v27 = -1;
          do
            ++v27;
          while ( v12[v27] );
          v28 = 2 * v27 + 2;
        }
        else
        {
          v12 = &S2;
          v28 = 2;
        }
        v52 = v12;
        v53 = v28;
        v54 = 0;
        if ( v26 )
        {
          v29 = -1;
          do
            ++v29;
          while ( v26[v29] );
          v30 = 2 * v29 + 2;
        }
        else
        {
          v26 = &S2;
          v30 = 2;
        }
        v50 = v30;
        v49 = v26;
        v47 = L"Marking pipe invalid and erasing pipe";
        v51 = 0;
        v45 = "CMidiClientManager::OnDeviceRemoved";
        v48 = 76;
        v46 = 36;
        tlgWriteTransfer_EventWriteTransfer((__int64)v25, (unsigned __int8 *)byte_140087C85, 0, 0, 6u, &v44);
        std::wstring::~wstring((char **)S1);
      }
      CMidiPipe::Invalidate((CMidiPipe *)v11[8]);
      v3 = v37;
      ++v36;
    }
LABEL_23:
    v23 = (__int64 **)v11[2];
    if ( *((_BYTE *)v23 + 25) )
    {
      for ( i = (__int64 *)v11[1]; !*((_BYTE *)i + 25) && v11 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v11 = i;
      v11 = i;
    }
    else
    {
      v11 = (__int64 *)v11[2];
      for ( j = *v23; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v11 = j;
    }
  }
  v32 = (unsigned int *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  result = *v32;
  if ( (unsigned int)result > 4 )
  {
    v41 = (const char *)L"Exit";
    v39 = (const char *)a1;
    v38 = "CMidiClientManager::OnDeviceRemoved";
    return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
             (__int64)v32,
             (__int64)qword_1400873F8,
             v33,
             v34,
             &v38,
             (__int64)&v39,
             &v41);
  }
  return result;
}

```

## disassembly

```asm
0x14001bf60  push    rbp
0x14001bf62  push    rbx
0x14001bf63  push    rsi
0x14001bf64  push    rdi
0x14001bf65  push    r12
0x14001bf67  push    r13
0x14001bf69  push    r14
0x14001bf6b  push    r15
0x14001bf6d  lea     rbp, [rsp-8]
0x14001bf72  sub     rsp, 108h
0x14001bf79  mov     rax, cs:__security_cookie
0x14001bf80  xor     rax, rsp
0x14001bf83  mov     [rbp+40h+var_50], rax
0x14001bf87  xor     esi, esi
0x14001bf89  mov     r12, rdx
0x14001bf8c  mov     r14d, esi
0x14001bf8f  mov     [rsp+140h+var_FC], esi
0x14001bf93  mov     r13, rcx
0x14001bf96  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001bf9b  lea     r15, aCmidiclientman_0; "CMidiClientManager::OnDeviceRemoved"
0x14001bfa2  mov     rcx, [rax+8]
0x14001bfa6  mov     eax, [rcx]
0x14001bfa8  cmp     eax, 4
0x14001bfab  jbe     short loc_14001C008
0x14001bfad  mov     rax, [r12+8]
0x14001bfb2  lea     rdx, word_14008805E
0x14001bfb9  sub     rax, [r12]
0x14001bfbd  sar     rax, 5
0x14001bfc1  mov     [rsp+140h+var_100], eax
0x14001bfc5  lea     rax, aEnter; "Enter"
0x14001bfcc  mov     [rsp+140h+var_E8], rax
0x14001bfd1  lea     rax, [rsp+140h+var_100]
0x14001bfd6  mov     [rsp+140h+var_108], rax
0x14001bfdb  lea     rax, [rsp+140h+var_E8]
0x14001bfe0  mov     [rsp+140h+var_110], rax
0x14001bfe5  lea     rax, [rsp+140h+var_F8]
0x14001bfea  mov     [rsp+140h+var_118], rax
0x14001bfef  lea     rax, [rsp+140h+var_F0]
0x14001bff4  mov     [rsp+140h+var_120], rax
0x14001bff9  mov     [rsp+140h+var_F8], r13
0x14001bffe  mov     [rsp+140h+var_F0], r15
0x14001c003  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x14001c008  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001c00d  mov     rcx, [rax+8]
0x14001c011  mov     eax, [rcx]
0x14001c013  cmp     eax, 4
0x14001c016  jbe     short loc_14001C073
0x14001c018  mov     rax, [r12+8]
0x14001c01d  lea     rdx, byte_14008768D
0x14001c024  sub     rax, [r12]
0x14001c028  sar     rax, 5
0x14001c02c  mov     [rsp+140h+var_100], eax
0x14001c030  lea     rax, aAcquiredClient; "Acquired client manager lock"
0x14001c037  mov     [rsp+140h+var_F0], rax
0x14001c03c  lea     rax, [rsp+140h+var_100]
0x14001c041  mov     [rsp+140h+var_108], rax
0x14001c046  lea     rax, [rsp+140h+var_F0]
0x14001c04b  mov     [rsp+140h+var_110], rax
0x14001c050  lea     rax, [rsp+140h+var_F8]
0x14001c055  mov     [rsp+140h+var_118], rax
0x14001c05a  lea     rax, [rsp+140h+var_E8]
0x14001c05f  mov     [rsp+140h+var_120], rax
0x14001c064  mov     [rsp+140h+var_F8], r13
0x14001c069  mov     [rsp+140h+var_E8], r15
0x14001c06e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x14001c073  mov     rbx, [r13+58h]
0x14001c077  mov     edi, esi
0x14001c079  mov     [rsp+140h+var_100], esi
0x14001c07d  mov     rbx, [rbx]
0x14001c080  cmp     [rbx+19h], sil
0x14001c084  jnz     loc_14001C303
0x14001c08a  mov     rdi, [r12]
0x14001c08e  mov     r15, [r12+8]
0x14001c093  cmp     rdi, r15
0x14001c096  jz      loc_14001C18B
0x14001c09c  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001c0a1  lea     rsi, [rdi+18h]
0x14001c0a5  mov     rcx, [rax+8]
0x14001c0a9  mov     eax, [rcx]
0x14001c0ab  cmp     eax, 4
0x14001c0ae  jbe     short loc_14001C114
0x14001c0b0  cmp     qword ptr [rsi], 7
0x14001c0b4  jbe     short loc_14001C0BB
0x14001c0b6  mov     rax, [rdi]
0x14001c0b9  jmp     short loc_14001C0BE
0x14001c0bb  mov     rax, rdi
0x14001c0be  mov     [rsp+140h+var_F0], rax
0x14001c0c3  lea     rdx, byte_140088251
0x14001c0ca  lea     rax, aCheckingForDev; "Checking for device pipe with interface"...
0x14001c0d1  mov     [rsp+140h+var_E8], r13
0x14001c0d6  mov     [rsp+140h+var_F8], rax
0x14001c0db  lea     rax, aCmidiclientman_0; "CMidiClientManager::OnDeviceRemoved"
0x14001c0e2  mov     [rsp+140h+var_E0], rax
0x14001c0e7  lea     rax, [rsp+140h+var_F0]
0x14001c0ec  mov     [rsp+140h+var_108], rax
0x14001c0f1  lea     rax, [rsp+140h+var_F8]
0x14001c0f6  mov     [rsp+140h+var_110], rax
0x14001c0fb  lea     rax, [rsp+140h+var_E8]
0x14001c100  mov     [rsp+140h+var_118], rax
0x14001c105  lea     rax, [rsp+140h+var_E0]
0x14001c10a  mov     [rsp+140h+var_120], rax
0x14001c10f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14001c114  mov     rdx, [rbx+40h]
0x14001c118  lea     rcx, [rsp+140h+S1]
0x14001c11d  add     rdx, 10h
0x14001c121  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001c126  or      r14d, 1
0x14001c12a  cmp     qword ptr [rsi], 7
0x14001c12e  mov     [rsp+140h+var_FC], r14d
0x14001c133  jbe     short loc_14001C13A
0x14001c135  mov     rdx, [rdi]
0x14001c138  jmp     short loc_14001C13D
0x14001c13a  mov     rdx, rdi; S2
0x14001c13d  cmp     [rbp+40h+var_C0], 7
0x14001c142  lea     rcx, [rsp+140h+S1]
0x14001c147  mov     r8, [rdi+10h]; N
0x14001c14b  cmova   rcx, [rsp+140h+S1]; S1
0x14001c151  cmp     [rsp+140h+var_C8], r8
0x14001c156  jnb     short loc_14001C15D
0x14001c158  xor     r14b, r14b
0x14001c15b  jmp     short loc_14001C168
0x14001c15d  call    wmemcmp
0x14001c162  test    eax, eax
0x14001c164  setz    r14b
0x14001c168  lea     rcx, [rsp+140h+S1]; void *
0x14001c16d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001c172  test    r14b, r14b
0x14001c175  jnz     short loc_14001C1A6
0x14001c177  mov     r14d, [rsp+140h+var_FC]
0x14001c17c  add     rdi, 20h ; ' '
0x14001c180  cmp     rdi, r15
0x14001c183  jnz     loc_14001C09C
0x14001c189  xor     esi, esi
0x14001c18b  mov     edi, [rsp+140h+var_100]
0x14001c18f  mov     rcx, [rbx+10h]
0x14001c193  cmp     [rcx+19h], sil
0x14001c197  jz      loc_14001C2DF
0x14001c19d  mov     rax, [rbx+8]
0x14001c1a1  jmp     loc_14001C2D1
0x14001c1a6  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001c1ab  mov     r14, [rax+8]
0x14001c1af  mov     eax, [r14]
0x14001c1b2  cmp     eax, 4
0x14001c1b5  jbe     loc_14001C2A5
0x14001c1bb  cmp     qword ptr [rsi], 7
0x14001c1bf  jbe     short loc_14001C1C4
0x14001c1c1  mov     rdi, [rdi]
0x14001c1c4  mov     rdx, [rbx+40h]
0x14001c1c8  lea     rcx, [rsp+140h+S1]
0x14001c1cd  add     rdx, 10h
0x14001c1d1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001c1d6  mov     edx, 2
0x14001c1db  lea     rcx, [rsp+140h+S1]
0x14001c1e0  or      [rsp+140h+var_FC], edx
0x14001c1e4  cmp     [rbp+40h+var_C0], 7
0x14001c1e9  cmova   rcx, [rsp+140h+S1]
0x14001c1ef  xor     esi, esi
0x14001c1f1  test    rdi, rdi
0x14001c1f4  jz      short loc_14001C20C
0x14001c1f6  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001c1fa  inc     rax
0x14001c1fd  cmp     [rdi+rax*2], si
0x14001c201  jnz     short loc_14001C1FA
0x14001c203  lea     eax, ds:2[rax*2]
0x14001c20a  jmp     short loc_14001C215
0x14001c20c  lea     rdi, S2
0x14001c213  mov     eax, edx
0x14001c215  mov     [rbp+40h+var_60], rdi
0x14001c219  mov     [rbp+40h+var_58], eax
0x14001c21c  mov     [rbp+40h+var_54], esi
0x14001c21f  test    rcx, rcx
0x14001c222  jz      short loc_14001C23A
0x14001c224  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001c228  inc     rax
0x14001c22b  cmp     [rcx+rax*2], si
0x14001c22f  jnz     short loc_14001C228
0x14001c231  lea     eax, ds:2[rax*2]
0x14001c238  jmp     short loc_14001C243
0x14001c23a  lea     rcx, S2
0x14001c241  mov     eax, edx
0x14001c243  mov     [rbp+40h+var_68], eax
0x14001c246  lea     rdx, byte_140087C85
0x14001c24d  lea     rax, aMarkingPipeInv; "Marking pipe invalid and erasing pipe"
0x14001c254  mov     [rbp+40h+var_70], rcx
0x14001c258  mov     [rbp+40h+var_80], rax
0x14001c25c  xor     r9d, r9d
0x14001c25f  lea     rax, aCmidiclientman_0; "CMidiClientManager::OnDeviceRemoved"
0x14001c266  mov     [rbp+40h+var_64], esi
0x14001c269  mov     [rbp+40h+var_90], rax
0x14001c26d  xor     r8d, r8d
0x14001c270  lea     rax, [rbp+40h+var_B0]
0x14001c274  mov     [rbp+40h+var_78], 4Ch ; 'L'
0x14001c27c  mov     [rsp+140h+var_118], rax
0x14001c281  mov     rcx, r14
0x14001c284  mov     dword ptr [rsp+140h+var_120], 6
0x14001c28c  mov     [rbp+40h+var_88], 24h ; '$'
0x14001c294  call    _tlgWriteTransfer_EventWriteTransfer
0x14001c299  lea     rcx, [rsp+140h+S1]; void *
0x14001c29e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001c2a3  jmp     short loc_14001C2A7
0x14001c2a5  xor     esi, esi
0x14001c2a7  mov     rcx, [rbx+40h]; this
0x14001c2ab  call    ?Invalidate@CMidiPipe@@QEAAXXZ; CMidiPipe::Invalidate(void)
0x14001c2b0  mov     edi, [rsp+140h+var_100]
0x14001c2b4  mov     r14d, [rsp+140h+var_FC]
0x14001c2b9  inc     edi
0x14001c2bb  mov     [rsp+140h+var_100], edi
0x14001c2bf  jmp     loc_14001C18F
0x14001c2c4  cmp     rbx, [rax+10h]
0x14001c2c8  jnz     short loc_14001C2D7
0x14001c2ca  mov     rbx, rax
0x14001c2cd  mov     rax, [rax+8]
0x14001c2d1  cmp     [rax+19h], sil
0x14001c2d5  jz      short loc_14001C2C4
0x14001c2d7  mov     rbx, rax
0x14001c2da  jmp     loc_14001C080
0x14001c2df  mov     rbx, rcx
0x14001c2e2  mov     rcx, [rcx]
0x14001c2e5  cmp     [rcx+19h], sil
0x14001c2e9  jnz     loc_14001C080
0x14001c2ef  mov     rax, [rcx]
0x14001c2f2  mov     rbx, rcx
0x14001c2f5  mov     rcx, rax
0x14001c2f8  cmp     [rax+19h], sil
0x14001c2fc  jz      short loc_14001C2EF
0x14001c2fe  jmp     loc_14001C080
0x14001c303  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001c308  mov     rcx, [rax+8]
0x14001c30c  mov     eax, [rcx]
0x14001c30e  cmp     eax, 4
0x14001c311  jbe     short loc_14001C368
0x14001c313  lea     rax, aExit; "Exit"
0x14001c31a  mov     [rsp+140h+var_100], edi
0x14001c31e  mov     [rsp+140h+var_E0], rax
0x14001c323  lea     rdx, qword_1400873F8
0x14001c32a  lea     rax, aCmidiclientman_0; "CMidiClientManager::OnDeviceRemoved"
0x14001c331  mov     [rsp+140h+var_F0], r13
0x14001c336  mov     [rsp+140h+var_F8], rax
0x14001c33b  lea     rax, [rsp+140h+var_100]
0x14001c340  mov     [rsp+140h+var_108], rax
0x14001c345  lea     rax, [rsp+140h+var_E0]
0x14001c34a  mov     [rsp+140h+var_110], rax
0x14001c34f  lea     rax, [rsp+140h+var_F0]
0x14001c354  mov     [rsp+140h+var_118], rax
0x14001c359  lea     rax, [rsp+140h+var_F8]
0x14001c35e  mov     [rsp+140h+var_120], rax
0x14001c363  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x14001c368  mov     rcx, [rbp+40h+var_50]
0x14001c36c  xor     rcx, rsp; StackCookie
0x14001c36f  call    __security_check_cookie
0x14001c374  add     rsp, 108h
0x14001c37b  pop     r15
0x14001c37d  pop     r14
0x14001c37f  pop     r13
0x14001c381  pop     r12
0x14001c383  pop     rdi
0x14001c384  pop     rsi
0x14001c385  pop     rbx
0x14001c386  pop     rbp
0x14001c387  retn
```
