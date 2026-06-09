# NgcMCloud::RecoveryProtector::FromCbor(SimpleCbor::Decoder &)

- ea: `0x1801368fc`
- end: `0x180136e59`
- name: `?FromCbor@RecoveryProtector@NgcMCloud@@SA?AU12@AEAVDecoder@SimpleCbor@@@Z`
- size: `1373`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x180047494`

## callees

- `0x18001d5e4`
- `0x18001df88`
- `0x180023bc8`
- `0x18002a07c`
- `0x180037f6c`
- `0x18008e36c`
- `0x18008e3a4`
- `0x18008e458`
- `0x18008e508`
- `0x180091034`
- `0x1800910c0`
- `0x1800912f4`
- `0x1800c1e48`
- `0x1800c1e84`
- `0x1800c1f3c`
- `0x1800c3718`
- `0x180135c14`
- `0x180135eb4`
- `0x1801360b0`
- `0x180136174`
- `0x18013630c`
- `0x1801368fc`
- `0x180136e60`
- `0x18013c090`

## string_xrefs

- `0x18013698f`: `onecore\ds\security\ngc\lockbox\common\lib\recoveryblob.cpp`
- `0x1801369fc`: `onecore\ds\security\ngc\lockbox\common\lib\recoveryblob.cpp`
- `0x180136a28`: `onecore\ds\security\ngc\lockbox\common\lib\recoveryblob.cpp`
- `0x180136aa9`: `onecore\ds\security\ngc\lockbox\common\lib\recoveryblob.cpp`
- `0x180136ac8`: `onecore\ds\security\ngc\lockbox\common\lib\recoveryblob.cpp`
- `0x180136b2a`: `onecore\ds\security\ngc\lockbox\common\lib\recoveryblob.cpp`
- `0x180136b73`: `onecore\ds\security\ngc\lockbox\common\lib\recoveryblob.cpp`
- `0x180136b92`: `onecore\ds\security\ngc\lockbox\common\lib\recoveryblob.cpp`
- `0x180136bbd`: `onecore\ds\security\ngc\lockbox\common\lib\recoveryblob.cpp`
- `0x180136bdf`: `onecore\ds\security\ngc\lockbox\common\lib\recoveryblob.cpp`
- `0x180136c28`: `onecore\ds\security\ngc\lockbox\common\lib\recoveryblob.cpp`
- `0x180136c47`: `onecore\ds\security\ngc\lockbox\common\lib\recoveryblob.cpp`
- `0x180136ceb`: `onecore\ds\security\ngc\lockbox\common\lib\recoveryblob.cpp`
- `0x180136d17`: `onecore\ds\security\ngc\lockbox\common\lib\recoveryblob.cpp`
- `0x180136d4c`: `onecore\ds\security\ngc\lockbox\common\lib\recoveryblob.cpp`
- `0x180136d67`: `onecore\ds\security\ngc\lockbox\common\lib\recoveryblob.cpp`
- `0x180136d94`: `onecore\ds\security\ngc\lockbox\common\lib\recoveryblob.cpp`
- `0x180136dbb`: `onecore\ds\security\ngc\lockbox\common\lib\recoveryblob.cpp`
- `0x180136de7`: `onecore\ds\security\ngc\lockbox\common\lib\recoveryblob.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcMCloud::RecoveryProtector::FromCbor(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  int v4; // ebx
  int v5; // esi
  int v6; // r14d
  int v7; // r15d
  int v8; // edi
  int v9; // r12d
  int v10; // r13d
  int *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 TextWString; // rax
  __int64 v15; // rax
  char *v16; // r14
  unsigned __int64 v17; // rsi
  __int64 v18; // rax
  __int64 v19; // rax
  int v22; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+44h] [rbp-BCh]
  const char *v24; // [rsp+48h] [rbp-B8h]
  char *Uint; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+60h] [rbp-A0h] BYREF
  int v27; // [rsp+64h] [rbp-9Ch]
  const char *v28; // [rsp+68h] [rbp-98h]
  __int64 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+88h] [rbp-78h]
  _DWORD v31[2]; // [rsp+90h] [rbp-70h] BYREF
  const char *v32; // [rsp+98h] [rbp-68h]
  _DWORD v33[2]; // [rsp+A0h] [rbp-60h] BYREF
  const char *v34; // [rsp+A8h] [rbp-58h]
  _DWORD v35[2]; // [rsp+B0h] [rbp-50h] BYREF
  const char *v36; // [rsp+B8h] [rbp-48h]
  _DWORD v37[2]; // [rsp+C0h] [rbp-40h] BYREF
  const char *v38; // [rsp+C8h] [rbp-38h]
  _DWORD v39[2]; // [rsp+D0h] [rbp-30h] BYREF
  const char *v40; // [rsp+D8h] [rbp-28h]
  _DWORD v41[2]; // [rsp+E0h] [rbp-20h] BYREF
  const char *v42; // [rsp+E8h] [rbp-18h]
  _DWORD v43[2]; // [rsp+F0h] [rbp-10h] BYREF
  const char *v44; // [rsp+F8h] [rbp-8h]
  _DWORD v45[2]; // [rsp+100h] [rbp+0h] BYREF
  const char *v46; // [rsp+108h] [rbp+8h]
  _DWORD v47[2]; // [rsp+110h] [rbp+10h] BYREF
  const char *v48; // [rsp+118h] [rbp+18h]
  _DWORD v49[2]; // [rsp+120h] [rbp+20h] BYREF
  const char *v50; // [rsp+128h] [rbp+28h]
  _DWORD v51[2]; // [rsp+130h] [rbp+30h] BYREF
  const char *v52; // [rsp+138h] [rbp+38h]
  _DWORD v53[2]; // [rsp+140h] [rbp+40h] BYREF
  const char *v54; // [rsp+148h] [rbp+48h]
  _DWORD v55[2]; // [rsp+150h] [rbp+50h] BYREF
  const char *v56; // [rsp+158h] [rbp+58h]
  _DWORD v57[2]; // [rsp+160h] [rbp+60h] BYREF
  const char *v58; // [rsp+168h] [rbp+68h]
  _BYTE v59[208]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v60[64]; // [rsp+240h] [rbp+140h] BYREF
  __int128 v61; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v62[8]; // [rsp+290h] [rbp+190h] BYREF
  __int64 v63; // [rsp+298h] [rbp+198h]
  __int64 v64; // [rsp+2A0h] [rbp+1A0h]
  _BYTE v65[32]; // [rsp+2A8h] [rbp+1A8h] BYREF
  __int64 v66; // [rsp+2C8h] [rbp+1C8h]
  _BYTE v67[32]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v68[208]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+408h] [rbp+308h]

  v2 = a2;
  v3 = a1;
  v30 = a1;
  v29 = a1;
  v61 = 0;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v62);
  std::wstring::wstring(v65);
  v66 = 0;
  std::wstring::wstring(v67);
  v68[200] = 0;
  v26 = 179;
  v27 = v23;
  v28 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp";
  SimpleCbor::Decoder::EnterMap(v2, &v26);
  v26 = 180;
  v4 = v23;
  v27 = v23;
  v28 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp";
  if ( !(unsigned __int8)SimpleCbor::Decoder::EndOfContainer(v2, &v26) )
  {
    v5 = v23;
    v6 = v23;
    v7 = v23;
    v8 = v23;
    v9 = v23;
    v10 = v23;
    while ( 1 )
    {
      v31[0] = 182;
      v31[1] = v23;
      v32 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp";
      Uint = (char *)SimpleCbor::Decoder::GetUint(a2, v31);
      v33[0] = 183;
      v33[1] = v23;
      v34 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp";
      SimpleCbor::Decoder::NextItem(a2, v33);
      if ( Uint == (char *)1 )
      {
        v57[0] = 187;
        v57[1] = v5;
        v58 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp";
        *(_QWORD *)&v61 = SimpleCbor::Decoder::GetUint(a2, v57);
        v22 = 188;
        v23 = v6;
        v24 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp";
        v11 = &v22;
        goto LABEL_25;
      }
      if ( Uint == (char *)2 )
      {
        v53[0] = 191;
        v53[1] = v23;
        v54 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp";
        v19 = SimpleCbor::Decoder::GetUint(a2, v53);
        DWORD2(v61) = wil::safe_cast<unsigned long,unsigned __int64,0>(v19);
        v55[0] = 192;
        v55[1] = v23;
        v56 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp";
        v11 = v55;
        goto LABEL_25;
      }
      if ( Uint == (char *)3 )
      {
        v49[0] = 196;
        v49[1] = v7;
        v50 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp";
        v15 = SimpleCbor::Decoder::EnterSizedArray(a2, v49);
        Uint = 0;
        if ( v15 )
        {
          v16 = Uint;
          v17 = v15;
          do
          {
            v18 = NgcMCloud::RecoveryProtector::Secret::FromCbor(v60, a2);
            if ( v63 == v64 )
            {
              std::vector<NgcMCloud::RecoveryProtector::Secret>::_Emplace_reallocate<NgcMCloud::RecoveryProtector::Secret>(
                v62,
                v63,
                v18);
            }
            else
            {
              NgcMCloud::RecoveryProtector::Secret::Secret(v63, v18);
              v63 += 56;
            }
            NgcMCloud::RecoveryProtector::Secret::~Secret((NgcMCloud::RecoveryProtector::Secret *)v60);
            ++v16;
          }
          while ( (unsigned __int64)v16 < v17 );
          v4 = v23;
          v5 = v23;
          v6 = v23;
        }
        v51[0] = 201;
        v51[1] = v8;
        v52 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp";
        SimpleCbor::Decoder::LeaveContainer(a2, v51);
        goto LABEL_26;
      }
      if ( Uint == (char *)100 )
      {
        v45[0] = 205;
        v45[1] = v23;
        v46 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp";
        TextWString = SimpleCbor::Decoder::GetTextWString(a2, v60, v45);
        std::wstring::operator=(v65, TextWString);
        std::wstring::_Tidy_deallocate(v60);
        v47[0] = 206;
        v47[1] = v23;
        v48 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp";
        v11 = v47;
        goto LABEL_25;
      }
      if ( Uint == (char *)101 )
      {
        v41[0] = 210;
        v41[1] = v9;
        v42 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp";
        v66 = SimpleCbor::Decoder::GetUint(a2, v41);
        v43[0] = 211;
        v43[1] = v10;
        v44 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp";
        v11 = v43;
        goto LABEL_25;
      }
      if ( Uint == (char *)102 )
        break;
      if ( Uint != (char *)200 )
      {
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0xDE,
          (unsigned int)"onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp",
          (const char *)0x8000FFFFLL,
          (int)"Unknown item %llu",
          Uint);
        v35[0] = 223;
        v35[1] = v23;
        v36 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp";
        v11 = v35;
LABEL_25:
        SimpleCbor::Decoder::NextItem(a2, v11);
        goto LABEL_26;
      }
      v12 = NgcMCloud::DecodeMetadata(v59, a2);
      Uint = v68;
      std::_Variant_raw_visit1<1>::_Visit<std::_Variant_assign_visitor<std::monostate,NgcMCloud::UnknownMetadata,NgcMCloud::PcMetadata,NgcMCloud::FidoHmacMetadata>,std::_Variant_storage_<0,std::monostate,NgcMCloud::UnknownMetadata,NgcMCloud::PcMetadata,NgcMCloud::FidoHmacMetadata>>(
        *(char *)(v12 + 200) + 1LL,
        &Uint,
        v12);
      std::_Variant_base<std::monostate,NgcMCloud::UnknownMetadata,NgcMCloud::PcMetadata,NgcMCloud::FidoHmacMetadata>::_Destroy(v59);
LABEL_26:
      v26 = 180;
      v27 = v4;
      v28 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp";
      if ( (unsigned __int8)SimpleCbor::Decoder::EndOfContainer(a2, &v26) )
      {
        v2 = a2;
        v3 = v30;
        goto LABEL_28;
      }
    }
    v37[0] = 214;
    v37[1] = v23;
    v38 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp";
    v13 = SimpleCbor::Decoder::GetTextWString(a2, v60, v37);
    std::wstring::operator=(v67, v13);
    std::wstring::_Tidy_deallocate(v60);
    v39[0] = 215;
    v39[1] = v23;
    v40 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp";
    v11 = v39;
    goto LABEL_25;
  }
LABEL_28:
  v22 = 226;
  v24 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\recoveryblob.cpp";
  SimpleCbor::Decoder::LeaveContainer(v2, &v22);
  NgcMCloud::RecoveryProtector::RecoveryProtector(v3, &v61);
  NgcMCloud::RecoveryProtector::~RecoveryProtector((NgcMCloud::RecoveryProtector *)&v61);
  return v3;
}

```

## disassembly

```asm
0x1801368fc  mov     [rsp-8+arg_10], rbx
0x180136901  push    rbp
0x180136902  push    rsi
0x180136903  push    rdi
0x180136904  push    r12
0x180136906  push    r13
0x180136908  push    r14
0x18013690a  push    r15
0x18013690c  lea     rbp, [rsp-2D0h]
0x180136914  sub     rsp, 3D0h
0x18013691b  mov     rax, cs:__security_cookie
0x180136922  xor     rax, rsp
0x180136925  mov     [rbp+300h+var_40], rax
0x18013692c  mov     rdi, rdx
0x18013692f  mov     [rsp+400h+var_3D0], rdx
0x180136934  mov     rsi, rcx
0x180136937  mov     [rbp+300h+var_378], rcx
0x18013693b  mov     [rsp+400h+var_390], rcx
0x180136940  xor     r15d, r15d
0x180136943  xorps   xmm0, xmm0
0x180136946  movups  [rbp+300h+var_180], xmm0
0x18013694d  lea     rcx, [rbp+300h+var_170]
0x180136954  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180136959  lea     rcx, [rbp+300h+var_158]
0x180136960  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180136965  mov     [rbp+300h+var_138], r15
0x18013696c  lea     rcx, [rbp+300h+var_130]
0x180136973  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180136978  mov     [rbp+300h+var_48], r15b
0x18013697f  mov     [rsp+400h+var_3A0], 0B3h
0x180136987  mov     eax, [rsp+400h+var_3BC]
0x18013698b  mov     [rsp+400h+var_39C], eax
0x18013698f  lea     r14, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180136996  mov     [rsp+400h+var_398], r14
0x18013699b  lea     rdx, [rsp+400h+var_3A0]
0x1801369a0  mov     rcx, rdi
0x1801369a3  call    ?EnterMap@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EnterMap(SimpleCbor::impl::slim_source_location)
0x1801369a8  mov     [rsp+400h+var_3A0], 0B4h
0x1801369b0  mov     ebx, [rsp+400h+var_3BC]
0x1801369b4  mov     [rsp+400h+var_39C], ebx
0x1801369b8  mov     [rsp+400h+var_398], r14
0x1801369bd  lea     rdx, [rsp+400h+var_3A0]
0x1801369c2  mov     rcx, rdi
0x1801369c5  call    ?EndOfContainer@Decoder@SimpleCbor@@QEAA_NUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EndOfContainer(SimpleCbor::impl::slim_source_location)
0x1801369ca  test    al, al
0x1801369cc  jnz     loc_180136DEE
0x1801369d2  mov     esi, [rsp+400h+var_3BC]
0x1801369d6  mov     r14d, [rsp+400h+var_3BC]
0x1801369db  mov     r15d, [rsp+400h+var_3BC]
0x1801369e0  mov     edi, [rsp+400h+var_3BC]
0x1801369e4  mov     r12d, [rsp+400h+var_3BC]
0x1801369e9  mov     r13d, [rsp+400h+var_3BC]
0x1801369ee  mov     [rbp+300h+var_370], 0B6h
0x1801369f5  mov     eax, [rsp+400h+var_3BC]
0x1801369f9  mov     [rbp+300h+var_36C], eax
0x1801369fc  lea     rax, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180136a03  mov     [rbp+300h+var_368], rax
0x180136a07  lea     rdx, [rbp+300h+var_370]
0x180136a0b  mov     rcx, [rsp+400h+var_3D0]
0x180136a10  call    ?GetUint@Decoder@SimpleCbor@@QEAA_KUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetUint(SimpleCbor::impl::slim_source_location)
0x180136a15  mov     [rsp+400h+var_3B0], rax
0x180136a1a  mov     [rbp+300h+var_360], 0B7h
0x180136a21  mov     eax, [rsp+400h+var_3BC]
0x180136a25  mov     [rbp+300h+var_35C], eax
0x180136a28  lea     rax, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180136a2f  mov     [rbp+300h+var_358], rax
0x180136a33  lea     rdx, [rbp+300h+var_360]
0x180136a37  mov     rcx, [rsp+400h+var_3D0]
0x180136a3c  call    ?NextItem@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::NextItem(SimpleCbor::impl::slim_source_location)
0x180136a41  mov     rax, [rsp+400h+var_3B0]
0x180136a46  mov     rcx, rax
0x180136a49  sub     rcx, 1
0x180136a4d  jz      loc_180136D5D
0x180136a53  sub     rcx, 1
0x180136a57  jz      loc_180136D09
0x180136a5d  sub     rcx, 1
0x180136a61  jz      loc_180136C3C
0x180136a67  sub     rcx, 61h ; 'a'
0x180136a6b  jz      loc_180136BD1
0x180136a71  sub     rcx, 1
0x180136a75  jz      loc_180136B87
0x180136a7b  sub     rcx, 1
0x180136a7f  jz      loc_180136B1C
0x180136a85  cmp     rcx, 62h ; 'b'
0x180136a89  jz      short loc_180136ADC
0x180136a8b  mov     rcx, [rbp+308h]; this
0x180136a92  mov     [rsp+400h+var_3D8], rax; char *
0x180136a97  lea     rax, aUnknownItemLlu; "Unknown item %llu"
0x180136a9e  mov     qword ptr [rsp+400h+var_3E0], rax; int
0x180136aa3  mov     r9d, 8000FFFFh; char *
0x180136aa9  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180136ab0  mov     edx, 0DEh; void *
0x180136ab5  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180136aba  mov     [rbp+300h+var_350], 0DFh
0x180136ac1  mov     eax, [rsp+400h+var_3BC]
0x180136ac5  mov     [rbp+300h+var_34C], eax
0x180136ac8  lea     rax, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180136acf  mov     [rbp+300h+var_348], rax
0x180136ad3  lea     rdx, [rbp+300h+var_350]
0x180136ad7  jmp     loc_180136DA5
0x180136adc  mov     rdx, [rsp+400h+var_3D0]
0x180136ae1  lea     rcx, [rbp+300h+var_290]
0x180136ae5  call    NgcMCloud__DecodeMetadata
0x180136aea  lea     rcx, [rbp+300h+var_110]
0x180136af1  mov     [rsp+400h+var_3B0], rcx
0x180136af6  movsx   rcx, byte ptr [rax+0C8h]
0x180136afe  inc     rcx
0x180136b01  mov     r8, rax
0x180136b04  lea     rdx, [rsp+400h+var_3B0]
0x180136b09  call    ??$_Visit@U?$_Variant_assign_visitor@Umonostate@std@@UUnknownMetadata@NgcMCloud@@UPcMetadata@4@UFidoHmacMetadata@4@@std@@V?$_Variant_storage_@$0A@Umonostate@std@@UUnknownMetadata@NgcMCloud@@UPcMetadata@4@UFidoHmacMetadata@4@@2@@?$_Variant_raw_visit1@$00@std@@SAX_K$$QEAU?$_Variant_assign_visitor@Umonostate@std@@UUnknownMetadata@NgcMCloud@@UPcMetadata@4@UFidoHmacMetadata@4@@1@$$QEAV?$_Variant_storage_@$0A@Umonostate@std@@UUnknownMetadata@NgcMCloud@@UPcMetadata@4@UFidoHmacMetadata@4@@1@@Z; std::_Variant_raw_visit1<1>::_Visit<std::_Variant_assign_visitor<std::monostate,NgcMCloud::UnknownMetadata,NgcMCloud::PcMetadata,NgcMCloud::FidoHmacMetadata>,std::_Variant_storage_<0,std::monostate,NgcMCloud::UnknownMetadata,NgcMCloud::PcMetadata,NgcMCloud::FidoHmacMetadata>>(unsigned __int64,std::_Variant_assign_visitor<std::monostate,NgcMCloud::UnknownMetadata,NgcMCloud::PcMetadata,NgcMCloud::FidoHmacMetadata> &&,std::_Variant_storage_<0,std::monostate,NgcMCloud::UnknownMetadata,NgcMCloud::PcMetadata,NgcMCloud::FidoHmacMetadata> &&)
0x180136b0e  lea     rcx, [rbp+300h+var_290]
0x180136b12  call    ?_Destroy@?$_Variant_base@Umonostate@std@@UUnknownMetadata@NgcMCloud@@UPcMetadata@4@UFidoHmacMetadata@4@@std@@QEAAXXZ; std::_Variant_base<std::monostate,NgcMCloud::UnknownMetadata,NgcMCloud::PcMetadata,NgcMCloud::FidoHmacMetadata>::_Destroy(void)
0x180136b17  jmp     loc_180136DAF
0x180136b1c  mov     [rbp+300h+var_340], 0D6h
0x180136b23  mov     eax, [rsp+400h+var_3BC]
0x180136b27  mov     [rbp+300h+var_33C], eax
0x180136b2a  lea     rax, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180136b31  mov     [rbp+300h+var_338], rax
0x180136b35  lea     r8, [rbp+300h+var_340]
0x180136b39  lea     rdx, [rbp+300h+var_1C0]
0x180136b40  mov     rcx, [rsp+400h+var_3D0]
0x180136b45  call    ?GetTextWString@Decoder@SimpleCbor@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetTextWString(SimpleCbor::impl::slim_source_location)
0x180136b4a  mov     rdx, rax
0x180136b4d  lea     rcx, [rbp+300h+var_130]
0x180136b54  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180136b59  lea     rcx, [rbp+300h+var_1C0]
0x180136b60  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180136b65  mov     [rbp+300h+var_330], 0D7h
0x180136b6c  mov     eax, [rsp+400h+var_3BC]
0x180136b70  mov     [rbp+300h+var_32C], eax
0x180136b73  lea     rax, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180136b7a  mov     [rbp+300h+var_328], rax
0x180136b7e  lea     rdx, [rbp+300h+var_330]
0x180136b82  jmp     loc_180136DA5
0x180136b87  mov     [rbp+300h+var_320], 0D2h
0x180136b8e  mov     [rbp+300h+var_31C], r12d
0x180136b92  lea     rax, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180136b99  mov     [rbp+300h+var_318], rax
0x180136b9d  lea     rdx, [rbp+300h+var_320]
0x180136ba1  mov     rcx, [rsp+400h+var_3D0]
0x180136ba6  call    ?GetUint@Decoder@SimpleCbor@@QEAA_KUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetUint(SimpleCbor::impl::slim_source_location)
0x180136bab  mov     [rbp+300h+var_138], rax
0x180136bb2  mov     [rbp+300h+var_310], 0D3h
0x180136bb9  mov     [rbp+300h+var_30C], r13d
0x180136bbd  lea     rax, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180136bc4  mov     [rbp+300h+var_308], rax
0x180136bc8  lea     rdx, [rbp+300h+var_310]
0x180136bcc  jmp     loc_180136DA5
0x180136bd1  mov     [rbp+300h+var_300], 0CDh
0x180136bd8  mov     eax, [rsp+400h+var_3BC]
0x180136bdc  mov     [rbp+300h+var_2FC], eax
0x180136bdf  lea     rax, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180136be6  mov     [rbp+300h+var_2F8], rax
0x180136bea  lea     r8, [rbp+300h+var_300]
0x180136bee  lea     rdx, [rbp+300h+var_1C0]
0x180136bf5  mov     rcx, [rsp+400h+var_3D0]
0x180136bfa  call    ?GetTextWString@Decoder@SimpleCbor@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetTextWString(SimpleCbor::impl::slim_source_location)
0x180136bff  mov     rdx, rax
0x180136c02  lea     rcx, [rbp+300h+var_158]
0x180136c09  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180136c0e  lea     rcx, [rbp+300h+var_1C0]
0x180136c15  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180136c1a  mov     [rbp+300h+var_2F0], 0CEh
0x180136c21  mov     eax, [rsp+400h+var_3BC]
0x180136c25  mov     [rbp+300h+var_2EC], eax
0x180136c28  lea     rax, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180136c2f  mov     [rbp+300h+var_2E8], rax
0x180136c33  lea     rdx, [rbp+300h+var_2F0]
0x180136c37  jmp     loc_180136DA5
0x180136c3c  mov     [rbp+300h+var_2E0], 0C4h
0x180136c43  mov     [rbp+300h+var_2DC], r15d
0x180136c47  lea     rax, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180136c4e  mov     [rbp+300h+var_2D8], rax
0x180136c52  lea     rdx, [rbp+300h+var_2E0]
0x180136c56  mov     rcx, [rsp+400h+var_3D0]
0x180136c5b  call    ?EnterSizedArray@Decoder@SimpleCbor@@QEAA_KUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EnterSizedArray(SimpleCbor::impl::slim_source_location)
0x180136c60  mov     [rsp+400h+var_3B0], 0
0x180136c69  test    rax, rax
0x180136c6c  jz      short loc_180136CE1
0x180136c6e  mov     rbx, [rsp+400h+var_3D0]
0x180136c73  mov     r14, [rsp+400h+var_3B0]
0x180136c78  mov     rsi, rax
0x180136c7b  mov     rdx, rbx
0x180136c7e  lea     rcx, [rbp+300h+var_1C0]
0x180136c85  call    ?FromCbor@Secret@RecoveryProtector@NgcMCloud@@SA?AU123@AEAVDecoder@SimpleCbor@@@Z; NgcMCloud::RecoveryProtector::Secret::FromCbor(SimpleCbor::Decoder &)
0x180136c8a  nop
0x180136c8b  mov     rcx, [rbp+300h+var_168]
0x180136c92  cmp     rcx, [rbp+300h+var_160]
0x180136c99  jz      short loc_180136CAD
0x180136c9b  mov     rdx, rax
0x180136c9e  call    ??0Secret@RecoveryProtector@NgcMCloud@@QEAA@$$QEAU012@@Z; NgcMCloud::RecoveryProtector::Secret::Secret(NgcMCloud::RecoveryProtector::Secret &&)
0x180136ca3  add     [rbp+300h+var_168], 38h ; '8'
0x180136cab  jmp     short loc_180136CC0
0x180136cad  mov     r8, rax
0x180136cb0  mov     rdx, rcx
0x180136cb3  lea     rcx, [rbp+300h+var_170]
0x180136cba  call    ??$_Emplace_reallocate@USecret@RecoveryProtector@NgcMCloud@@@?$vector@USecret@RecoveryProtector@NgcMCloud@@V?$allocator@USecret@RecoveryProtector@NgcMCloud@@@std@@@std@@AEAAPEAUSecret@RecoveryProtector@NgcMCloud@@QEAU234@$$QEAU234@@Z; std::vector<NgcMCloud::RecoveryProtector::Secret>::_Emplace_reallocate<NgcMCloud::RecoveryProtector::Secret>(NgcMCloud::RecoveryProtector::Secret * const,NgcMCloud::RecoveryProtector::Secret &&)
0x180136cbf  nop
0x180136cc0  lea     rcx, [rbp+300h+var_1C0]; this
0x180136cc7  call    ??1Secret@RecoveryProtector@NgcMCloud@@QEAA@XZ; NgcMCloud::RecoveryProtector::Secret::~Secret(void)
0x180136ccc  inc     r14
0x180136ccf  cmp     r14, rsi
0x180136cd2  jb      short loc_180136C7B
0x180136cd4  mov     ebx, [rsp+400h+var_3BC]
0x180136cd8  mov     esi, [rsp+400h+var_3BC]
0x180136cdc  mov     r14d, [rsp+400h+var_3BC]
0x180136ce1  mov     [rbp+300h+var_2D0], 0C9h
0x180136ce8  mov     [rbp+300h+var_2CC], edi
0x180136ceb  lea     rax, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180136cf2  mov     [rbp+300h+var_2C8], rax
0x180136cf6  lea     rdx, [rbp+300h+var_2D0]
0x180136cfa  mov     rcx, [rsp+400h+var_3D0]
0x180136cff  call    ?LeaveContainer@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::LeaveContainer(SimpleCbor::impl::slim_source_location)
0x180136d04  jmp     loc_180136DAF
0x180136d09  mov     [rbp+300h+var_2C0], 0BFh
0x180136d10  mov     eax, [rsp+400h+var_3BC]
0x180136d14  mov     [rbp+300h+var_2BC], eax
0x180136d17  lea     rax, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180136d1e  mov     [rbp+300h+var_2B8], rax
0x180136d22  lea     rdx, [rbp+300h+var_2C0]
0x180136d26  mov     rcx, [rsp+400h+var_3D0]
0x180136d2b  call    ?GetUint@Decoder@SimpleCbor@@QEAA_KUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetUint(SimpleCbor::impl::slim_source_location)
0x180136d30  mov     rcx, rax
0x180136d33  call    ??$safe_cast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast<ulong,unsigned __int64,0>(unsigned __int64)
0x180136d38  mov     dword ptr [rbp+300h+var_180+8], eax
0x180136d3e  mov     [rbp+300h+var_2B0], 0C0h
0x180136d45  mov     eax, [rsp+400h+var_3BC]
0x180136d49  mov     [rbp+300h+var_2AC], eax
0x180136d4c  lea     rax, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180136d53  mov     [rbp+300h+var_2A8], rax
0x180136d57  lea     rdx, [rbp+300h+var_2B0]
0x180136d5b  jmp     short loc_180136DA5
0x180136d5d  mov     [rbp+300h+var_2A0], 0BBh
0x180136d64  mov     [rbp+300h+var_29C], esi
0x180136d67  lea     rax, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180136d6e  mov     [rbp+300h+var_298], rax
0x180136d72  lea     rdx, [rbp+300h+var_2A0]
0x180136d76  mov     rcx, [rsp+400h+var_3D0]
0x180136d7b  call    ?GetUint@Decoder@SimpleCbor@@QEAA_KUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetUint(SimpleCbor::impl::slim_source_location)
0x180136d80  mov     qword ptr [rbp+300h+var_180], rax
0x180136d87  mov     [rsp+400h+var_3C0], 0BCh
0x180136d8f  mov     [rsp+400h+var_3BC], r14d
0x180136d94  lea     rax, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180136d9b  mov     [rsp+400h+var_3B8], rax
0x180136da0  lea     rdx, [rsp+400h+var_3C0]
0x180136da5  mov     rcx, [rsp+400h+var_3D0]
0x180136daa  call    ?NextItem@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::NextItem(SimpleCbor::impl::slim_source_location)
0x180136daf  mov     [rsp+400h+var_3A0], 0B4h
0x180136db7  mov     [rsp+400h+var_39C], ebx
0x180136dbb  lea     rax, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180136dc2  mov     [rsp+400h+var_398], rax
0x180136dc7  lea     rdx, [rsp+400h+var_3A0]
0x180136dcc  mov     rcx, [rsp+400h+var_3D0]
0x180136dd1  call    ?EndOfContainer@Decoder@SimpleCbor@@QEAA_NUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EndOfContainer(SimpleCbor::impl::slim_source_location)
0x180136dd6  test    al, al
0x180136dd8  jz      loc_1801369EE
0x180136dde  mov     rdi, [rsp+400h+var_3D0]
0x180136de3  mov     rsi, [rbp+300h+var_378]
0x180136de7  lea     r14, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180136dee  mov     [rsp+400h+var_3C0], 0E2h
0x180136df6  mov     edx, [rsp+400h+var_3BC]
0x180136dfa  mov     [rsp+400h+var_3BC], edx
0x180136dfe  mov     [rsp+400h+var_3B8], r14
0x180136e03  lea     rdx, [rsp+400h+var_3C0]
0x180136e08  mov     rcx, rdi
0x180136e0b  call    ?LeaveContainer@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::LeaveContainer(SimpleCbor::impl::slim_source_location)
0x180136e10  lea     rdx, [rbp+300h+var_180]
0x180136e17  mov     rcx, rsi
0x180136e1a  call    ??0RecoveryProtector@NgcMCloud@@QEAA@$$QEAU01@@Z; NgcMCloud::RecoveryProtector::RecoveryProtector(NgcMCloud::RecoveryProtector &&)
0x180136e1f  nop
0x180136e20  lea     rcx, [rbp+300h+var_180]; this
0x180136e27  call    ??1RecoveryProtector@NgcMCloud@@QEAA@XZ; NgcMCloud::RecoveryProtector::~RecoveryProtector(void)
0x180136e2c  mov     rax, rsi
0x180136e2f  mov     rcx, [rbp+300h+var_40]
0x180136e36  xor     rcx, rsp; StackCookie
0x180136e39  call    __security_check_cookie
0x180136e3e  mov     rbx, [rsp+400h+arg_10]
0x180136e46  add     rsp, 3D0h
0x180136e4d  pop     r15
0x180136e4f  pop     r14
0x180136e51  pop     r13
0x180136e53  pop     r12
0x180136e55  pop     rdi
0x180136e56  pop     rsi
0x180136e57  pop     rbp
0x180136e58  retn
```
