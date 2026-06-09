# AppV::Client::Publishing::Configurations::ServerConfiguration::CheckNewServerEntry(AppV::Client::Publishing::Configurations::ServerProperties const &)

- ea: `0x14005ae3c`
- end: `0x14005b1b1`
- name: `?CheckNewServerEntry@ServerConfiguration@Configurations@Publishing@Client@AppV@@AEAA_KAEBUServerProperties@2345@@Z`
- size: `885`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Publishing::Configurations::ServerConfiguration *__hidden this, const struct AppV::Client::Publishing::Configurations::ServerProperties *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005ae10`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x1400147fc`
- `0x140018bec`
- `0x14005ac74`
- `0x14005ae3c`
- `0x14005b1e0`
- `0x14005b8a4`
- `0x14006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005b06d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005b06d`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005b10b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005b10b`

## string_xrefs

- `0x14005b104`: `admin\appman\appv\client\publishing\configurations\serverconfiguration.cpp`
- `0x14005b11b`: `admin\appman\appv\client\publishing\configurations\serverconfiguration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AppV::Client::Publishing::Configurations::ServerConfiguration::CheckNewServerEntry(
        AppV::Client::Publishing::Configurations::ServerConfiguration *this,
        const struct AppV::Client::Publishing::Configurations::ServerProperties *a2)
{
  __int64 result; // rax
  unsigned __int64 v5; // rbx
  __m128i si128; // xmm6
  _QWORD *v7; // rdx
  __int64 v8; // r14
  unsigned __int64 v9; // r8
  __int64 v10; // rcx
  int *v11; // rbx
  int v12; // r15d
  const void **v13; // rsi
  _WORD *v14; // rdx
  unsigned __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rdi
  __int64 v18; // r8
  const wchar_t *v19; // rax
  __int64 v20; // rcx
  unsigned int v21; // ecx
  __int64 v22; // rcx
  int v23; // ecx
  __int128 *v24; // rdx
  __int128 *v25; // rcx
  __int64 v26; // r8
  char *v27; // rax
  const char *v28; // rax
  int v29; // [rsp+38h] [rbp-79h] BYREF
  __int128 v30; // [rsp+40h] [rbp-71h] BYREF
  __int64 v31; // [rsp+50h] [rbp-61h]
  __int128 v32; // [rsp+58h] [rbp-59h] BYREF
  __m128i v33; // [rsp+68h] [rbp-49h]
  __int128 v34; // [rsp+78h] [rbp-39h] BYREF
  __m128i v35; // [rsp+88h] [rbp-29h]
  struct _EVENT_DATA_DESCRIPTOR v36; // [rsp+98h] [rbp-19h] BYREF
  __int128 v37; // [rsp+A8h] [rbp-9h]
  void *v38; // [rsp+B8h] [rbp+7h]
  int v39; // [rsp+C0h] [rbp+Fh]
  int v40; // [rsp+C4h] [rbp+13h]

  result = AppV::Client::Publishing::Configurations::ServerConfiguration::ValidateServerEntry(this, a2, 0);
  if ( (result & 0x8000000000LL) != 0 )
  {
    v30 = 0;
    v31 = 0;
    v5 = (*(__int64 (__fastcall **)(AppV::Client::Publishing::Configurations::ServerConfiguration *, __int128 *))(*(_QWORD *)this + 8LL))(
           this,
           &v30);
    if ( (v5 & 0x8000000000LL) != 0 )
    {
      v34 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v35 = si128;
      LOWORD(v34) = 0;
      v7 = (_QWORD *)((char *)a2 + 40);
      if ( *((_QWORD *)a2 + 8) > 7u )
        v7 = (_QWORD *)*v7;
      v32 = 0;
      v33 = 0;
      v8 = -1;
      v9 = -1;
      do
        ++v9;
      while ( *((_WORD *)v7 + v9) );
      std::wstring::_Construct<1,wchar_t const *>((char **)&v32, v7, v9);
      v5 = AppV::Client::Publishing::Configurations::ServerConfiguration::MapIdn(v10, &v32, &v34);
      std::wstring::~wstring((char **)&v32);
      if ( (v5 & 0x8000000000LL) != 0 )
      {
        v11 = (int *)v30;
        v12 = 10;
        while ( 1 )
        {
          if ( v11 == *((int **)&v30 + 1) )
          {
            std::wstring::~wstring((char **)&v34);
            std::vector<AppV::Client::Publishing::Configurations::ServerProperties>::~vector<AppV::Client::Publishing::Configurations::ServerProperties>((char ***)&v30);
            return 0x8000000000LL;
          }
          v32 = 0;
          v33 = si128;
          LOWORD(v32) = 0;
          v13 = (const void **)(v11 + 10);
          if ( *((_QWORD *)v11 + 8) <= 7u )
            v14 = v11 + 10;
          else
            v14 = *v13;
          v36 = 0;
          v37 = 0;
          v15 = -1;
          do
            ++v15;
          while ( v14[v15] );
          std::wstring::_Construct<1,wchar_t const *>((char **)&v36, v14, v15);
          v17 = AppV::Client::Publishing::Configurations::ServerConfiguration::MapIdn(v16, &v36, &v32);
          std::wstring::~wstring((char **)&v36);
          if ( v17 )
          {
            v24 = &v34;
            if ( v35.m128i_i64[1] > 7uLL )
              v24 = (__int128 *)v34;
            v25 = &v32;
            if ( v33.m128i_i64[1] > 7uLL )
              v25 = (__int128 *)v32;
            if ( !(unsigned int)_o__wcsicmp(v25, v24) )
            {
              if ( (byte_1400B0B86 & 0x40) != 0 )
              {
                if ( *((_QWORD *)v11 + 8) > 7u )
                  v13 = (const void **)*v13;
                v29 = *v11;
                *(_QWORD *)&v37 = &v29;
                *((_QWORD *)&v37 + 1) = 4;
                if ( v13 )
                {
                  do
                    ++v8;
                  while ( *((_WORD *)v13 + v8) );
                  v12 = 2 * v8 + 2;
                }
                else
                {
                  v13 = (const void **)L"NULL";
                }
                v38 = v13;
                v39 = v12;
                v40 = 0;
                McGenEventWrite_EventWriteTransfer(
                  (REGHANDLE *)PROVIDER_MICROSOFT_APPV_CLIENT_Context,
                  (const EVENT_DESCRIPTOR *)APPV_CLIENT_Evt_refreshConfigServerDuplicatedUrl,
                  v26,
                  3u,
                  &v36);
              }
              v27 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverconfiguration.cpp", 92);
              if ( v27 )
                v28 = v27 + 1;
              else
                v28 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverconfiguration.cpp";
              v5 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v28) << 52)
                 | 0x120700000704LL;
              std::wstring::~wstring((char **)&v32);
              break;
            }
          }
          else
          {
            if ( byte_1400B0B86 < 0 )
            {
              v19 = (const wchar_t *)(v11 + 2);
              if ( *((_QWORD *)v11 + 4) > 7u )
                v19 = *(const wchar_t **)v19;
              if ( *((_QWORD *)v11 + 8) > 7u )
                v13 = (const void **)*v13;
              if ( v13 )
              {
                v20 = -1;
                do
                  ++v20;
                while ( *((_WORD *)v13 + v20) );
                v21 = 2 * v20 + 2;
              }
              else
              {
                v13 = (const void **)L"NULL";
                v21 = 10;
              }
              *(_QWORD *)&v37 = v13;
              *((_QWORD *)&v37 + 1) = v21;
              if ( v19 )
              {
                v22 = -1;
                do
                  ++v22;
                while ( v19[v22] );
                v23 = 2 * v22 + 2;
              }
              else
              {
                v19 = L"NULL";
                v23 = 10;
              }
              v38 = (void *)v19;
              v39 = v23;
              v40 = 0;
              McGenEventWrite_EventWriteTransfer(
                (REGHANDLE *)PROVIDER_MICROSOFT_APPV_CLIENT_Context,
                (const EVENT_DESCRIPTOR *)APPV_CLIENT_Evt_publishingServerBadURL,
                v18,
                3u,
                &v36);
            }
            v11 += 24;
          }
          std::wstring::~wstring((char **)&v32);
          v11 += 24;
        }
      }
      std::wstring::~wstring((char **)&v34);
    }
    std::vector<AppV::Client::Publishing::Configurations::ServerProperties>::~vector<AppV::Client::Publishing::Configurations::ServerProperties>((char ***)&v30);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x14005ae3c  mov     rax, rsp
0x14005ae3f  mov     [rax+18h], rbx
0x14005ae43  mov     [rax+20h], rsi
0x14005ae47  push    rbp
0x14005ae48  push    rdi
0x14005ae49  push    r12
0x14005ae4b  push    r14
0x14005ae4d  push    r15
0x14005ae4f  lea     rbp, [rax-5Fh]
0x14005ae53  sub     rsp, 0E0h
0x14005ae5a  movaps  xmmword ptr [rax-38h], xmm6
0x14005ae5e  mov     rax, cs:__security_cookie
0x14005ae65  xor     rax, rsp
0x14005ae68  mov     [rbp+57h+var_40], rax
0x14005ae6c  mov     rdi, rdx
0x14005ae6f  mov     rbx, rcx
0x14005ae72  xor     r8d, r8d; bool
0x14005ae75  call    ?ValidateServerEntry@ServerConfiguration@Configurations@Publishing@Client@AppV@@AEAA_KAEBUServerProperties@2345@_N@Z; AppV::Client::Publishing::Configurations::ServerConfiguration::ValidateServerEntry(AppV::Client::Publishing::Configurations::ServerProperties const &,bool)
0x14005ae7a  bt      rax, 27h ; '''
0x14005ae7f  jnb     loc_14005B165
0x14005ae85  xorps   xmm0, xmm0
0x14005ae88  movdqu  [rbp+57h+var_C8], xmm0
0x14005ae8d  xor     r12d, r12d
0x14005ae90  mov     [rbp+57h+var_B8], r12
0x14005ae94  mov     rax, [rbx]
0x14005ae97  lea     rdx, [rbp+57h+var_C8]
0x14005ae9b  mov     rcx, rbx
0x14005ae9e  mov     rax, [rax+8]
0x14005aea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005aea7  mov     rbx, rax
0x14005aeaa  bt      rax, 27h ; '''
0x14005aeaf  jnb     loc_14005B159
0x14005aeb5  xorps   xmm0, xmm0
0x14005aeb8  movups  [rbp+57h+var_90], xmm0
0x14005aebc  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14005aec4  movdqu  [rbp+57h+var_80], xmm6
0x14005aec9  mov     word ptr [rbp+57h+var_90], r12w
0x14005aece  lea     rdx, [rdi+28h]
0x14005aed2  cmp     qword ptr [rdx+18h], 7
0x14005aed7  jbe     short loc_14005AEDC
0x14005aed9  mov     rdx, [rdx]
0x14005aedc  movups  [rbp+57h+var_B0], xmm0
0x14005aee0  xorps   xmm1, xmm1
0x14005aee3  movdqu  [rbp+57h+var_A0], xmm1
0x14005aee8  or      r14, 0FFFFFFFFFFFFFFFFh
0x14005aeec  mov     r8, r14
0x14005aeef  inc     r8
0x14005aef2  cmp     [rdx+r8*2], r12w
0x14005aef7  jnz     short loc_14005AEEF
0x14005aef9  lea     rcx, [rbp+57h+var_B0]
0x14005aefd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005af02  nop
0x14005af03  lea     r8, [rbp+57h+var_90]
0x14005af07  lea     rdx, [rbp+57h+var_B0]
0x14005af0b  call    ?MapIdn@ServerConfiguration@Configurations@Publishing@Client@AppV@@AEAA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV67@@Z; AppV::Client::Publishing::Configurations::ServerConfiguration::MapIdn(std::wstring const &,std::wstring &)
0x14005af10  mov     rbx, rax
0x14005af13  lea     rcx, [rbp+57h+var_B0]
0x14005af17  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005af1c  bt      rbx, 27h ; '''
0x14005af21  jnb     loc_14005B14F
0x14005af27  mov     rbx, qword ptr [rbp+57h+var_C8]
0x14005af2b  mov     r15d, 0Ah
0x14005af31  cmp     rbx, qword ptr [rbp+57h+var_C8+8]
0x14005af35  jz      loc_14005B192
0x14005af3b  xorps   xmm0, xmm0
0x14005af3e  movups  [rbp+57h+var_B0], xmm0
0x14005af42  movdqu  [rbp+57h+var_A0], xmm6
0x14005af47  mov     word ptr [rbp+57h+var_B0], r12w
0x14005af4c  lea     rsi, [rbx+28h]
0x14005af50  cmp     qword ptr [rbx+40h], 7
0x14005af55  jbe     short loc_14005AF5C
0x14005af57  mov     rdx, [rsi]
0x14005af5a  jmp     short loc_14005AF5F
0x14005af5c  mov     rdx, rsi
0x14005af5f  movups  [rbp+57h+var_70], xmm0
0x14005af63  xorps   xmm1, xmm1
0x14005af66  movdqu  [rbp+57h+var_60], xmm1
0x14005af6b  mov     r8, r14
0x14005af6e  inc     r8
0x14005af71  cmp     [rdx+r8*2], r12w
0x14005af76  jnz     short loc_14005AF6E
0x14005af78  lea     rcx, [rbp+57h+var_70]
0x14005af7c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005af81  nop
0x14005af82  lea     r8, [rbp+57h+var_B0]
0x14005af86  lea     rdx, [rbp+57h+var_70]
0x14005af8a  call    ?MapIdn@ServerConfiguration@Configurations@Publishing@Client@AppV@@AEAA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV67@@Z; AppV::Client::Publishing::Configurations::ServerConfiguration::MapIdn(std::wstring const &,std::wstring &)
0x14005af8f  mov     rdi, rax
0x14005af92  lea     rcx, [rbp+57h+var_70]
0x14005af96  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005af9b  test    rdi, rdi
0x14005af9e  jnz     loc_14005B051
0x14005afa4  cmp     cs:byte_1400B0B86, r12b
0x14005afab  jge     loc_14005B04B
0x14005afb1  lea     rax, [rbx+8]
0x14005afb5  cmp     qword ptr [rbx+20h], 7
0x14005afba  jbe     short loc_14005AFBF
0x14005afbc  mov     rax, [rax]
0x14005afbf  cmp     qword ptr [rbx+40h], 7
0x14005afc4  jbe     short loc_14005AFC9
0x14005afc6  mov     rsi, [rsi]
0x14005afc9  test    rsi, rsi
0x14005afcc  jz      short loc_14005AFE4
0x14005afce  mov     rcx, r14
0x14005afd1  inc     rcx
0x14005afd4  cmp     [rsi+rcx*2], r12w
0x14005afd9  jnz     short loc_14005AFD1
0x14005afdb  lea     ecx, ds:2[rcx*2]
0x14005afe2  jmp     short loc_14005AFEE
0x14005afe4  lea     rsi, aNull; "NULL"
0x14005afeb  mov     ecx, r15d
0x14005afee  mov     qword ptr [rbp+57h+var_60], rsi
0x14005aff2  mov     dword ptr [rbp+57h+var_60+8], ecx
0x14005aff5  mov     dword ptr [rbp+57h+var_60+0Ch], r12d
0x14005aff9  test    rax, rax
0x14005affc  jz      short loc_14005B014
0x14005affe  mov     rcx, r14
0x14005b001  inc     rcx
0x14005b004  cmp     [rax+rcx*2], r12w
0x14005b009  jnz     short loc_14005B001
0x14005b00b  lea     ecx, ds:2[rcx*2]
0x14005b012  jmp     short loc_14005B01E
0x14005b014  lea     rax, aNull; "NULL"
0x14005b01b  mov     ecx, r15d
0x14005b01e  mov     [rbp+57h+var_50], rax
0x14005b022  mov     [rbp+57h+var_48], ecx
0x14005b025  mov     [rbp+57h+var_44], r12d
0x14005b029  lea     rax, [rbp+57h+var_70]
0x14005b02d  mov     [rsp+100h+var_E0], rax
0x14005b032  mov     r9d, 3
0x14005b038  lea     rdx, APPV_CLIENT_Evt_publishingServerBadURL
0x14005b03f  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x14005b046  call    McGenEventWrite_EventWriteTransfer
0x14005b04b  add     rbx, 60h ; '`'
0x14005b04f  jmp     short loc_14005B077
0x14005b051  lea     rdx, [rbp+57h+var_90]
0x14005b055  cmp     qword ptr [rbp+57h+var_80+8], 7
0x14005b05a  cmova   rdx, qword ptr [rbp+57h+var_90]
0x14005b05f  lea     rcx, [rbp+57h+var_B0]
0x14005b063  cmp     qword ptr [rbp+57h+var_A0+8], 7
0x14005b068  cmova   rcx, qword ptr [rbp+57h+var_B0]
0x14005b06d  call    cs:__imp__o__wcsicmp
0x14005b073  test    eax, eax
0x14005b075  jz      short loc_14005B089
0x14005b077  lea     rcx, [rbp+57h+var_B0]
0x14005b07b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005b080  add     rbx, 60h ; '`'
0x14005b084  jmp     loc_14005AF31
0x14005b089  test    cs:byte_1400B0B86, 40h
0x14005b090  jz      short loc_14005B0FF
0x14005b092  cmp     qword ptr [rsi+18h], 7
0x14005b097  jbe     short loc_14005B09C
0x14005b099  mov     rsi, [rsi]
0x14005b09c  mov     eax, [rbx]
0x14005b09e  mov     [rbp+57h+var_D0], eax
0x14005b0a1  lea     rax, [rbp+57h+var_D0]
0x14005b0a5  mov     qword ptr [rbp+57h+var_60], rax
0x14005b0a9  mov     qword ptr [rbp+57h+var_60+8], 4
0x14005b0b1  test    rsi, rsi
0x14005b0b4  jz      short loc_14005B0CA
0x14005b0b6  inc     r14
0x14005b0b9  cmp     [rsi+r14*2], r12w
0x14005b0be  jnz     short loc_14005B0B6
0x14005b0c0  lea     r15d, ds:2[r14*2]
0x14005b0c8  jmp     short loc_14005B0D1
0x14005b0ca  lea     rsi, aNull; "NULL"
0x14005b0d1  mov     [rbp+57h+var_50], rsi
0x14005b0d5  mov     [rbp+57h+var_48], r15d
0x14005b0d9  mov     [rbp+57h+var_44], r12d
0x14005b0dd  lea     rax, [rbp+57h+var_70]
0x14005b0e1  mov     [rsp+100h+var_E0], rax
0x14005b0e6  mov     r9d, 3
0x14005b0ec  lea     rdx, APPV_CLIENT_Evt_refreshConfigServerDuplicatedUrl
0x14005b0f3  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x14005b0fa  call    McGenEventWrite_EventWriteTransfer
0x14005b0ff  mov     edx, 5Ch ; '\'; Ch
0x14005b104  lea     rcx, aAdminAppmanApp_8; "admin\\appman\\appv\\client\\publishing"...
0x14005b10b  call    cs:__imp_strrchr
0x14005b111  test    rax, rax
0x14005b114  jz      short loc_14005B11B
0x14005b116  inc     rax
0x14005b119  jmp     short loc_14005B122
0x14005b11b  lea     rax, aAdminAppmanApp_8; "admin\\appman\\appv\\client\\publishing"...
0x14005b122  mov     rdx, rax; char *
0x14005b125  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005b12c  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005b131  mov     rbx, rax
0x14005b134  shl     rbx, 34h
0x14005b138  mov     rax, 120700000704h
0x14005b142  or      rbx, rax
0x14005b145  lea     rcx, [rbp+57h+var_B0]
0x14005b149  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005b14e  nop
0x14005b14f  lea     rcx, [rbp+57h+var_90]
0x14005b153  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005b158  nop
0x14005b159  lea     rcx, [rbp+57h+var_C8]
0x14005b15d  call    ??1?$vector@UServerProperties@Configurations@Publishing@Client@AppV@@V?$allocator@UServerProperties@Configurations@Publishing@Client@AppV@@@std@@@std@@QEAA@XZ; std::vector<AppV::Client::Publishing::Configurations::ServerProperties>::~vector<AppV::Client::Publishing::Configurations::ServerProperties>(void)
0x14005b162  mov     rax, rbx
0x14005b165  mov     rcx, [rbp+57h+var_40]
0x14005b169  xor     rcx, rsp; StackCookie
0x14005b16c  call    __security_check_cookie
0x14005b171  lea     r11, [rsp+100h+var_20]
0x14005b179  mov     rbx, [r11+40h]
0x14005b17d  mov     rsi, [r11+48h]
0x14005b181  movaps  xmm6, xmmword ptr [r11-10h]
0x14005b186  mov     rsp, r11
0x14005b189  pop     r15
0x14005b18b  pop     r14
0x14005b18d  pop     r12
0x14005b18f  pop     rdi
0x14005b190  pop     rbp
0x14005b191  retn
0x14005b192  lea     rcx, [rbp+57h+var_90]
0x14005b196  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005b19b  nop
0x14005b19c  lea     rcx, [rbp+57h+var_C8]
0x14005b1a0  call    ??1?$vector@UServerProperties@Configurations@Publishing@Client@AppV@@V?$allocator@UServerProperties@Configurations@Publishing@Client@AppV@@@std@@@std@@QEAA@XZ; std::vector<AppV::Client::Publishing::Configurations::ServerProperties>::~vector<AppV::Client::Publishing::Configurations::ServerProperties>(void)
0x14005b1a5  mov     rax, 8000000000h
0x14005b1af  jmp     short loc_14005B165
```
