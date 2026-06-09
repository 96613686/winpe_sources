# CGuestSpatialAudioClient::RuntimeClassInitialize(AudioClientConstructionParams const *)

- ea: `0x180083524`
- end: `0x180083999`
- name: `?RuntimeClassInitialize@CGuestSpatialAudioClient@@QEAAJPEBUAudioClientConstructionParams@@@Z`
- size: `1141`
- prototype: `__int64 __fastcall(CGuestSpatialAudioClient *__hidden this, const struct AudioClientConstructionParams *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009ddfc`

## callees

- `0x18000d11c`
- `0x180010a90`
- `0x180020400`
- `0x180025a04`
- `0x18004d8a8`
- `0x18008323c`
- `0x180083524`
- `0x1800839a0`
- `0x180087e80`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095fb8`
- `0x1800994e8`
- `0x1800af1c8`
- `0x1800b0470`
- `0x1800b2bb4`
- `0x18011ddd0`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18008361e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18008361e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800837f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008385c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800838da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008393d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083961`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800837f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008385c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800838da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008393d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083961`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall CGuestSpatialAudioClient::RuntimeClassInitialize(
        CGuestSpatialAudioClient *this,
        const struct AudioClientConstructionParams *a2)
{
  int v5; // eax
  unsigned int v6; // esi
  const PROPVARIANT *v7; // rdx
  HRESULT v8; // eax
  unsigned int v9; // esi
  int v10; // eax
  unsigned int v11; // esi
  GUID *v12; // r14
  int v13; // eax
  unsigned int v14; // ebx
  struct CGuestXvmAudioObject *RootProxyAudioObjectActivator; // rbx
  int v16; // ebx
  void *v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  unsigned int v20; // esi
  void *v21; // rcx
  __int64 v22; // rax
  int v23; // eax
  unsigned int v24; // ebx
  void *v25; // rcx
  int v26; // eax
  unsigned int v27; // ebx
  void *v28; // rcx
  void *v29; // rcx
  int v30; // [rsp+20h] [rbp-12C8h]
  LPVOID pv; // [rsp+30h] [rbp-12B8h] BYREF
  __int64 v32; // [rsp+38h] [rbp-12B0h] BYREF
  struct XvmEndpointId *v33; // [rsp+40h] [rbp-12A8h] BYREF
  const struct AudioClientConstructionParams *v34; // [rsp+48h] [rbp-12A0h] BYREF
  LPVOID *p_pv; // [rsp+50h] [rbp-1298h] BYREF
  __int64 v36; // [rsp+58h] [rbp-1290h] BYREF
  char v37; // [rsp+60h] [rbp-1288h]
  _BYTE v38[1560]; // [rsp+68h] [rbp-1280h] BYREF
  _BYTE v39[1568]; // [rsp+680h] [rbp-C68h] BYREF
  int Src; // [rsp+CA0h] [rbp-648h] BYREF
  __int64 v41; // [rsp+CA4h] [rbp-644h]
  int v42; // [rsp+CACh] [rbp-63Ch]
  int v43; // [rsp+CB0h] [rbp-638h]
  _BYTE v44[1548]; // [rsp+CB4h] [rbp-634h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+12E8h] [rbp+0h]

  v34 = a2;
  if ( a2 )
  {
    *(_OWORD *)((char *)this + 184) = *(_OWORD *)a2;
    *(_OWORD *)((char *)this + 200) = *((_OWORD *)a2 + 1);
    *(_OWORD *)((char *)this + 216) = *((_OWORD *)a2 + 2);
    *(_OWORD *)((char *)this + 232) = *((_OWORD *)a2 + 3);
    *((_QWORD *)this + 31) = *((_QWORD *)a2 + 8);
    *((_QWORD *)this + 25) = (char *)this + 160;
    *((_QWORD *)this + 26) = 0;
    v5 = _AllocString<CTCoAllocPolicy>(this, a2, *((_QWORD *)a2 + 3), (char *)this + 208);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v7 = (const PROPVARIANT *)*((_QWORD *)a2 + 2);
      if ( v7 && (v8 = PropVariantCopy(*((PROPVARIANT **)this + 25), v7), v9 = v8, v8 < 0) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x56,
          (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudioclient.cpp",
          (const char *)(unsigned int)v8,
          v30);
        return v9;
      }
      else
      {
        Src = 14;
        v41 = 1;
        v42 = 0;
        v43 = 135;
        memset_0(v44, 0, 0x600u);
        v33 = 0;
        v10 = XvmActivateProxyAudioObject::CastTo<XvmActivateClient2>(&Src, &v33);
        v11 = v10;
        if ( v10 >= 0 )
        {
          v12 = (GUID *)v33;
          v13 = CopyToXvmEndpointId(*((const unsigned __int16 **)a2 + 3), v33);
          v14 = v13;
          if ( v13 >= 0 )
          {
            v12[7] = GUID_00000000_0000_0000_0000_000000000000;
            RootProxyAudioObjectActivator = GetRootProxyAudioObjectActivator();
            if ( RootProxyAudioObjectActivator )
            {
              pv = 0;
              v33 = 0;
              p_pv = &pv;
              v36 = 0;
              v37 = 1;
              memcpy_0(v38, &Src, 0x614u);
              memcpy_0(v39, v38, 0x614u);
              v16 = CGuestXvmAudioObject::SendAndValidateResponse<XvmActivateProxyAudioObject>(
                      RootProxyAudioObjectActivator,
                      *((unsigned int *)RootProxyAudioObjectActivator + 12),
                      v39,
                      &v36);
              wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
              if ( v16 >= 0 )
              {
                v18 = *((_QWORD *)this + 19);
                *((_QWORD *)this + 19) = 0;
                if ( v18 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
                v19 = Microsoft::WRL::Details::MakeAndInitialize<CSpatialAudioClient,CSpatialAudioClient,AudioClientConstructionParams const * &>(
                        (char *)this + 152,
                        &v34);
                v20 = v19;
                if ( v19 >= 0 )
                {
                  v12[9].Data1 = *(_DWORD *)(*((_QWORD *)this + 19) + 244LL);
                  v32 = 0;
                  v34 = (const struct AudioClientConstructionParams *)&v32;
                  v22 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v34);
                  v23 = Microsoft::WRL::AsWeak<CGuestSpatialAudioClient>(this, v22);
                  v24 = v23;
                  if ( v23 >= 0 )
                  {
                    v26 = CGuestXvmAudioObject::Initialize(
                            (CGuestSpatialAudioClient *)((char *)this + 24),
                            *((_DWORD *)v33 + 3),
                            (struct Microsoft::WRL::WeakRef *)&v32,
                            0);
                    v27 = v26;
                    if ( v26 >= 0 )
                    {
                      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v32);
                      v29 = pv;
                      pv = 0;
                      if ( v29 )
                        CoTaskMemFree(v29);
                      return 0;
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x70,
                        (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudioclient.cpp",
                        (const char *)(unsigned int)v26,
                        (int)&v33);
                      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v32);
                      v28 = pv;
                      pv = 0;
                      if ( v28 )
                        CoTaskMemFree(v28);
                      return v27;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x6E,
                      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudioclient.cpp",
                      (const char *)(unsigned int)v23,
                      (int)&v33);
                    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v32);
                    v25 = pv;
                    pv = 0;
                    if ( v25 )
                      CoTaskMemFree(v25);
                    return v24;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x6A,
                    (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudioclient.cpp",
                    (const char *)(unsigned int)v19,
                    (int)&v33);
                  v21 = pv;
                  pv = 0;
                  if ( v21 )
                    CoTaskMemFree(v21);
                  return v20;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x68,
                  (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudioclient.cpp",
                  (const char *)(unsigned int)v16,
                  (int)&v33);
                v17 = pv;
                pv = 0;
                if ( v17 )
                  CoTaskMemFree(v17);
                return (unsigned int)v16;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x64,
                (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudioclient.cpp",
                (const char *)0x8000FFFFLL,
                v30);
              return 2147549183LL;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x5F,
              (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudioclient.cpp",
              (const char *)(unsigned int)v13,
              v30);
            return v14;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5D,
            (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudioclient.cpp",
            (const char *)(unsigned int)v10,
            v30);
          return v11;
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudioclient.cpp",
        (const char *)(unsigned int)v5,
        v30);
      return v6;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudioclient.cpp",
      (const char *)0x80070057LL,
      v30);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180083524  mov     [rsp+arg_10], rbx
0x180083529  mov     [rsp+arg_18], rsi
0x18008352e  push    rdi
0x18008352f  push    r14
0x180083531  push    r15
0x180083533  mov     eax, 12D0h
0x180083538  call    _alloca_probe
0x18008353d  sub     rsp, rax
0x180083540  mov     rax, cs:__security_cookie
0x180083547  xor     rax, rsp
0x18008354a  mov     [rsp+12E8h+var_28], rax
0x180083552  mov     rbx, rdx
0x180083555  mov     rdi, rcx
0x180083558  mov     [rsp+12E8h+var_12A0], rdx
0x18008355d  xor     r15d, r15d
0x180083560  test    rdx, rdx
0x180083563  jnz     short loc_18008358C
0x180083565  mov     rcx, [rsp+12E8h]; this
0x18008356d  mov     ebx, 80070057h
0x180083572  mov     r9d, ebx; char *
0x180083575  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\client\\spatialaudio"...
0x18008357c  lea     edx, [r15+4Dh]; void *
0x180083580  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083585  mov     eax, ebx
0x180083587  jmp     loc_18008396F
0x18008358c  movups  xmm0, xmmword ptr [rdx]
0x18008358f  movups  xmmword ptr [rcx+0B8h], xmm0
0x180083596  movups  xmm1, xmmword ptr [rdx+10h]
0x18008359a  movups  xmmword ptr [rcx+0C8h], xmm1
0x1800835a1  movups  xmm0, xmmword ptr [rdx+20h]
0x1800835a5  movups  xmmword ptr [rcx+0D8h], xmm0
0x1800835ac  movups  xmm1, xmmword ptr [rdx+30h]
0x1800835b0  movups  xmmword ptr [rcx+0E8h], xmm1
0x1800835b7  movsd   xmm0, qword ptr [rdx+40h]
0x1800835bc  movsd   qword ptr [rcx+0F8h], xmm0
0x1800835c4  lea     rax, [rcx+0A0h]
0x1800835cb  mov     [rcx+0C8h], rax
0x1800835d2  lea     r9, [rcx+0D0h]
0x1800835d9  mov     [r9], r15
0x1800835dc  mov     r8, [rdx+18h]
0x1800835e0  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800835e5  mov     esi, eax
0x1800835e7  test    eax, eax
0x1800835e9  jns     short loc_18008360E
0x1800835eb  mov     rcx, [rsp+12E8h]; this
0x1800835f3  mov     r9d, eax; char *
0x1800835f6  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\client\\spatialaudio"...
0x1800835fd  mov     edx, 52h ; 'R'; void *
0x180083602  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083607  mov     eax, esi
0x180083609  jmp     loc_18008396F
0x18008360e  mov     rdx, [rbx+10h]; pvarSrc
0x180083612  test    rdx, rdx
0x180083615  jz      short loc_18008364D
0x180083617  mov     rcx, [rdi+0C8h]; pvarDest
0x18008361e  call    cs:__imp_PropVariantCopy
0x180083624  mov     esi, eax
0x180083626  test    eax, eax
0x180083628  jns     short loc_18008364D
0x18008362a  mov     rcx, [rsp+12E8h]; this
0x180083632  mov     r9d, eax; char *
0x180083635  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\client\\spatialaudio"...
0x18008363c  mov     edx, 56h ; 'V'; void *
0x180083641  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083646  mov     eax, esi
0x180083648  jmp     loc_18008396F
0x18008364d  mov     [rsp+12E8h+Src], 0Eh
0x180083658  mov     [rsp+12E8h+var_644], 1
0x180083664  mov     [rsp+12E8h+var_63C], r15d
0x18008366c  mov     [rsp+12E8h+var_638], 87h
0x180083677  xor     edx, edx; Val
0x180083679  mov     r8d, 600h; Size
0x18008367f  lea     rcx, [rsp+12E8h+var_634]; void *
0x180083687  call    memset_0
0x18008368c  mov     [rsp+12E8h+var_12A8], r15
0x180083691  lea     rdx, [rsp+12E8h+var_12A8]
0x180083696  lea     rcx, [rsp+12E8h+Src]
0x18008369e  call    ??$CastTo@UXvmActivateClient2@@@XvmActivateProxyAudioObject@@QEAAJPEAPEAUXvmActivateClient2@@@Z; XvmActivateProxyAudioObject::CastTo<XvmActivateClient2>(XvmActivateClient2 * *)
0x1800836a3  mov     esi, eax
0x1800836a5  test    eax, eax
0x1800836a7  jns     short loc_1800836CC
0x1800836a9  mov     rcx, [rsp+12E8h]; this
0x1800836b1  mov     r9d, eax; char *
0x1800836b4  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\client\\spatialaudio"...
0x1800836bb  mov     edx, 5Dh ; ']'; void *
0x1800836c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800836c5  mov     eax, esi
0x1800836c7  jmp     loc_18008396F
0x1800836cc  mov     r14, [rsp+12E8h+var_12A8]
0x1800836d1  mov     rdx, r14; struct XvmEndpointId *
0x1800836d4  mov     rcx, [rbx+18h]; unsigned __int16 *
0x1800836d8  call    ?CopyToXvmEndpointId@@YAJPEBGPEAUXvmEndpointId@@@Z; CopyToXvmEndpointId(ushort const *,XvmEndpointId *)
0x1800836dd  mov     ebx, eax
0x1800836df  test    eax, eax
0x1800836e1  jns     short loc_180083706
0x1800836e3  mov     rcx, [rsp+12E8h]; this
0x1800836eb  mov     r9d, eax; char *
0x1800836ee  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\client\\spatialaudio"...
0x1800836f5  mov     edx, 5Fh ; '_'; void *
0x1800836fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800836ff  mov     eax, ebx
0x180083701  jmp     loc_18008396F
0x180083706  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18008370d  movdqu  xmmword ptr [r14+70h], xmm0
0x180083713  call    ?GetRootProxyAudioObjectActivator@@YAPEAVCGuestXvmAudioObject@@XZ; GetRootProxyAudioObjectActivator(void)
0x180083718  mov     rbx, rax
0x18008371b  test    rax, rax
0x18008371e  jnz     short loc_180083746
0x180083720  mov     rcx, [rsp+12E8h]; this
0x180083728  mov     ebx, 8000FFFFh
0x18008372d  mov     r9d, ebx; char *
0x180083730  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\client\\spatialaudio"...
0x180083737  lea     edx, [rax+64h]; void *
0x18008373a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008373f  mov     eax, ebx
0x180083741  jmp     loc_18008396F
0x180083746  mov     [rsp+12E8h+pv], r15
0x18008374b  mov     [rsp+12E8h+var_12A8], r15
0x180083750  lea     rax, [rsp+12E8h+pv]
0x180083755  mov     [rsp+12E8h+var_1298], rax
0x18008375a  mov     [rsp+12E8h+var_1290], r15
0x18008375f  mov     [rsp+12E8h+var_1288], 1
0x180083764  lea     rcx, [rsp+12E8h+var_1280]; void *
0x180083769  lea     rdx, [rsp+12E8h+Src]; Src
0x180083771  mov     esi, 614h
0x180083776  mov     r8d, esi; Size
0x180083779  call    memcpy_0
0x18008377e  lea     rcx, [rsp+12E8h+var_C68]; void *
0x180083786  lea     rdx, [rsp+12E8h+var_1280]; Src
0x18008378b  mov     r8d, esi; Size
0x18008378e  call    memcpy_0
0x180083793  lea     rax, [rsp+12E8h+var_12A8]
0x180083798  mov     qword ptr [rsp+12E8h+var_12C8], rax; int
0x18008379d  lea     r9, [rsp+12E8h+var_1290]
0x1800837a2  lea     r8, [rsp+12E8h+var_C68]
0x1800837aa  mov     edx, [rbx+30h]
0x1800837ad  mov     rcx, rbx
0x1800837b0  call    ??$SendAndValidateResponse@UXvmActivateProxyAudioObject@@@CGuestXvmAudioObject@@QEAAJIUXvmActivateProxyAudioObject@@PEAPEAUXvmMessage@@PEAPEAU1@@Z; CGuestXvmAudioObject::SendAndValidateResponse<XvmActivateProxyAudioObject>(uint,XvmActivateProxyAudioObject,XvmMessage * *,XvmActivateProxyAudioObject * *)
0x1800837b5  mov     ebx, eax
0x1800837b7  lea     rcx, [rsp+12E8h+var_1298]
0x1800837bc  call    ??1?$out_param_t@V?$unique_ptr@UXvmMessage@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800837c1  test    ebx, ebx
0x1800837c3  jns     short loc_1800837FE
0x1800837c5  mov     rcx, [rsp+12E8h]; this
0x1800837cd  mov     r9d, ebx; char *
0x1800837d0  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\client\\spatialaudio"...
0x1800837d7  mov     edx, 68h ; 'h'; void *
0x1800837dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800837e1  nop
0x1800837e2  mov     rcx, [rsp+12E8h+pv]; pv
0x1800837e7  mov     [rsp+12E8h+pv], r15
0x1800837ec  test    rcx, rcx
0x1800837ef  jz      short loc_1800837F7
0x1800837f1  call    cs:__imp_CoTaskMemFree
0x1800837f7  mov     eax, ebx
0x1800837f9  jmp     loc_18008396F
0x1800837fe  lea     rbx, [rdi+98h]
0x180083805  mov     rcx, [rbx]
0x180083808  mov     [rbx], r15
0x18008380b  test    rcx, rcx
0x18008380e  jz      short loc_18008381D
0x180083810  mov     rax, [rcx]
0x180083813  mov     rax, [rax+10h]
0x180083817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008381c  nop
0x18008381d  lea     rdx, [rsp+12E8h+var_12A0]
0x180083822  mov     rcx, rbx
0x180083825  call    ??$MakeAndInitialize@VCSpatialAudioClient@@V1@AEAPEBUAudioClientConstructionParams@@@Details@WRL@Microsoft@@YAJPEAPEAVCSpatialAudioClient@@AEAPEBUAudioClientConstructionParams@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CSpatialAudioClient,CSpatialAudioClient,AudioClientConstructionParams const * &>(CSpatialAudioClient * *,AudioClientConstructionParams const * &)
0x18008382a  mov     esi, eax
0x18008382c  test    eax, eax
0x18008382e  jns     short loc_180083869
0x180083830  mov     rcx, [rsp+12E8h]; this
0x180083838  mov     r9d, eax; char *
0x18008383b  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\client\\spatialaudio"...
0x180083842  mov     edx, 6Ah ; 'j'; void *
0x180083847  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008384c  nop
0x18008384d  mov     rcx, [rsp+12E8h+pv]; pv
0x180083852  mov     [rsp+12E8h+pv], r15
0x180083857  test    rcx, rcx
0x18008385a  jz      short loc_180083862
0x18008385c  call    cs:__imp_CoTaskMemFree
0x180083862  mov     eax, esi
0x180083864  jmp     loc_18008396F
0x180083869  mov     rax, [rbx]
0x18008386c  mov     ecx, [rax+0F4h]
0x180083872  mov     [r14+90h], ecx
0x180083879  mov     [rsp+12E8h+var_12B0], r15
0x18008387e  lea     rax, [rsp+12E8h+var_12B0]
0x180083883  mov     [rsp+12E8h+var_12A0], rax
0x180083888  lea     rcx, [rsp+12E8h+var_12A0]
0x18008388d  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x180083892  mov     rdx, rax
0x180083895  mov     rcx, rdi
0x180083898  call    ??$AsWeak@VCGuestSpatialAudioClient@@@WRL@Microsoft@@YAJPEAVCGuestSpatialAudioClient@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<CGuestSpatialAudioClient>(CGuestSpatialAudioClient *,Microsoft::WRL::WeakRef *)
0x18008389d  mov     ebx, eax
0x18008389f  test    eax, eax
0x1800838a1  jns     short loc_1800838E7
0x1800838a3  mov     rcx, [rsp+12E8h]; this
0x1800838ab  mov     r9d, eax; char *
0x1800838ae  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\client\\spatialaudio"...
0x1800838b5  mov     edx, 6Eh ; 'n'; void *
0x1800838ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800838bf  nop
0x1800838c0  lea     rcx, [rsp+12E8h+var_12B0]
0x1800838c5  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800838ca  nop
0x1800838cb  mov     rcx, [rsp+12E8h+pv]; pv
0x1800838d0  mov     [rsp+12E8h+pv], r15
0x1800838d5  test    rcx, rcx
0x1800838d8  jz      short loc_1800838E0
0x1800838da  call    cs:__imp_CoTaskMemFree
0x1800838e0  mov     eax, ebx
0x1800838e2  jmp     loc_18008396F
0x1800838e7  lea     rcx, [rdi+18h]; this
0x1800838eb  xor     r9d, r9d; struct XvmActivateProxyAudioObject *
0x1800838ee  lea     r8, [rsp+12E8h+var_12B0]; struct Microsoft::WRL::WeakRef *
0x1800838f3  mov     rdx, [rsp+12E8h+var_12A8]
0x1800838f8  mov     edx, [rdx+0Ch]; unsigned int
0x1800838fb  call    ?Initialize@CGuestXvmAudioObject@@IEAAJIAEAVWeakRef@WRL@Microsoft@@PEAUXvmActivateProxyAudioObject@@@Z; CGuestXvmAudioObject::Initialize(uint,Microsoft::WRL::WeakRef &,XvmActivateProxyAudioObject *)
0x180083900  mov     ebx, eax
0x180083902  test    eax, eax
0x180083904  jns     short loc_180083947
0x180083906  mov     rcx, [rsp+12E8h]; this
0x18008390e  mov     r9d, eax; char *
0x180083911  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\client\\spatialaudio"...
0x180083918  mov     edx, 70h ; 'p'; void *
0x18008391d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083922  nop
0x180083923  lea     rcx, [rsp+12E8h+var_12B0]
0x180083928  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18008392d  nop
0x18008392e  mov     rcx, [rsp+12E8h+pv]; pv
0x180083933  mov     [rsp+12E8h+pv], r15
0x180083938  test    rcx, rcx
0x18008393b  jz      short loc_180083943
0x18008393d  call    cs:__imp_CoTaskMemFree
0x180083943  mov     eax, ebx
0x180083945  jmp     short loc_18008396F
0x180083947  lea     rcx, [rsp+12E8h+var_12B0]
0x18008394c  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180083951  nop
0x180083952  mov     rcx, [rsp+12E8h+pv]; pv
0x180083957  mov     [rsp+12E8h+pv], r15
0x18008395c  test    rcx, rcx
0x18008395f  jz      short loc_180083967
0x180083961  call    cs:__imp_CoTaskMemFree
0x180083967  xor     eax, eax
0x180083969  jmp     short loc_18008396F
0x18008396b  mov     eax, dword ptr [rsp+12E8h+pv]
0x18008396f  mov     rcx, [rsp+12E8h+var_28]
0x180083977  xor     rcx, rsp; StackCookie
0x18008397a  call    __security_check_cookie
0x18008397f  lea     r11, [rsp+12E8h+var_18]
0x180083987  mov     rbx, [r11+30h]
0x18008398b  mov     rsi, [r11+38h]
0x18008398f  mov     rsp, r11
0x180083992  pop     r15
0x180083994  pop     r14
0x180083996  pop     rdi
0x180083997  retn
```
