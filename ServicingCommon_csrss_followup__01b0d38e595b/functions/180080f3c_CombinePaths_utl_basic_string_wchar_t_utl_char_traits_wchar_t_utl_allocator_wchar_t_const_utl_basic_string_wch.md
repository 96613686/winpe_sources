# CombinePaths(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x180080f3c`
- end: `0x180081248`
- name: `?CombinePaths@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0AEAV12@@Z`
- size: `780`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18007d468`
- `0x18007d5a8`
- `0x18007e3f0`
- `0x18007eb20`
- `0x180081d64`

## callees

- `0x18001f1d8`
- `0x18001f840`
- `0x18002d2b0`
- `0x180030ba8`
- `0x18007df88`
- `0x18007e15c`
- `0x18007e288`
- `0x18007e328`
- `0x180080f3c`

## string_xrefs

- `0x180080f80`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180080fcd`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180080ffd`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180081080`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800810d9`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x18008114d`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800811ed`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180080fa0`: `Path1.length() > 0`
- `0x180080f94`: `CombinePaths`
- `0x180080fe1`: `CombinePaths`
- `0x180081016`: `CombinePaths`
- `0x180081099`: `CombinePaths`
- `0x1800810f0`: `CombinePaths`
- `0x180081164`: `CombinePaths`
- `0x180081204`: `CombinePaths`
- `0x180081022`: `ULongAdd( static_cast<ULONG>(Path1.length()), PathLength, &PathLength)`
- `0x180080fed`: `Path2.length() > 0`
- `0x1800810a5`: `ModifiedPath2.resize(Path2.length())`
- `0x18008120f`: `ULongAdd( static_cast<ULONG>(Path2.length()), PathLength, &PathLength)`
- `0x180081179`: `FullPath.resize(PathLength)`
- `0x1800810fb`: `Path2.copy(ModifiedPath2.data(), Path2.length() - 1, 1)`

## pseudocode

```c
__int64 __fastcall CombinePaths(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r9
  __int64 v6; // rax
  const char *v8; // rax
  __int16 *v10; // r8
  __int64 v11; // rdx
  const char **v12; // rdx
  size_t v13; // rbx
  __int16 v14; // cx
  __int16 v15; // r8
  char v16; // r14
  const char **v17; // rdx
  unsigned int v18; // ebx
  const wchar_t *v19; // rsi
  __int16 *v20; // rax
  const char *v21; // [rsp+30h] [rbp-89h] BYREF
  const char *v22; // [rsp+38h] [rbp-81h]
  __int64 v23; // [rsp+40h] [rbp-79h]
  const char *v24; // [rsp+48h] [rbp-71h]
  const char *v25; // [rsp+50h] [rbp-69h] BYREF
  const char *v26; // [rsp+58h] [rbp-61h]
  __int64 v27; // [rsp+60h] [rbp-59h]
  const char *v28; // [rsp+68h] [rbp-51h]
  _QWORD v29[4]; // [rsp+70h] [rbp-49h] BYREF
  int v30; // [rsp+90h] [rbp-29h] BYREF
  wchar_t *Buffer[2]; // [rsp+98h] [rbp-21h] BYREF
  _WORD v32[8]; // [rsp+A8h] [rbp-11h] BYREF
  _QWORD v33[2]; // [rsp+B8h] [rbp-1h] BYREF
  _WORD v34[8]; // [rsp+C8h] [rbp+Fh] BYREF

  v3 = a1[1];
  v30 = 0;
  v6 = (v3 - *a1) >> 1;
  if ( !v6 )
  {
    v23 = 156;
    v21 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
    v22 = "CombinePaths";
    v8 = "Path1.length() > 0";
LABEL_3:
    v24 = v8;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v30,
             &v21);
  }
  v10 = *(__int16 **)a2;
  v11 = (__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 1;
  if ( !v11 )
  {
    v23 = 157;
    v21 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
    v22 = "CombinePaths";
    v8 = "Path2.length() > 0";
    goto LABEL_3;
  }
  if ( (int)v6 + 2 >= (unsigned int)v6 )
  {
    v13 = (unsigned int)(v6 + 2 + v11);
    if ( (unsigned int)v13 < (unsigned int)v11 )
    {
      v27 = 171;
      v25 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v12 = &v25;
      v26 = "CombinePaths";
      v28 = "ULongAdd( static_cast<ULONG>(Path2.length()), PathLength, &PathLength)";
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
               &v30,
               v12,
               2147942934LL);
    }
    v14 = *(_WORD *)(v3 - 2);
    v15 = *v10;
    v16 = 0;
    v33[0] = v34;
    v33[1] = v34;
    v34[0] = 0;
    if ( v14 == 92 )
    {
      if ( v15 == 92 )
      {
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                                 v33,
                                 v11) )
        {
          v23 = 182;
          v21 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
          v17 = &v21;
          v22 = "CombinePaths";
          v24 = "ModifiedPath2.resize(Path2.length())";
LABEL_15:
          v18 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                  &v30,
                  v17,
                  3221225495LL);
LABEL_25:
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v33);
          return v18;
        }
        v16 = 1;
        if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::copy(
                a2,
                v33[0],
                ((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 1) - 1,
                1) )
        {
          v29[2] = 183;
          v29[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
          v17 = (const char **)v29;
          v29[1] = "CombinePaths";
          v29[3] = "Path2.copy(ModifiedPath2.data(), Path2.length() - 1, 1)";
          goto LABEL_15;
        }
        LODWORD(v13) = v13 - 1;
      }
    }
    else if ( v15 != 92 )
    {
      v19 = L"%ws\\%ws";
LABEL_18:
      Buffer[0] = v32;
      Buffer[1] = v32;
      v32[0] = 0;
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                              Buffer,
                              v13) )
      {
        v20 = (__int16 *)v33[0];
        if ( !v16 )
          v20 = *(__int16 **)a2;
        swprintf_s(Buffer[0], v13, v19, *a1, v20);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::swap(a3, Buffer);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(Buffer);
        v18 = 0;
      }
      else
      {
        v27 = 201;
        v25 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
        v26 = "CombinePaths";
        v28 = "FullPath.resize(PathLength)";
        v18 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                &v30,
                &v25,
                3221225495LL);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(Buffer);
      }
      goto LABEL_25;
    }
    v13 = (unsigned int)(v13 - 1);
    v19 = L"%ws%ws";
    goto LABEL_18;
  }
  v23 = 165;
  v21 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
  v12 = &v21;
  v22 = "CombinePaths";
  v24 = "ULongAdd( static_cast<ULONG>(Path1.length()), PathLength, &PathLength)";
  return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
           &v30,
           v12,
           2147942934LL);
}

```

## disassembly

```asm
0x180080f3c  push    rbp
0x180080f3e  push    rbx
0x180080f3f  push    rsi
0x180080f40  push    rdi
0x180080f41  push    r12
0x180080f43  push    r14
0x180080f45  push    r15
0x180080f47  lea     rbp, [rsp-27h]
0x180080f4c  sub     rsp, 0E0h
0x180080f53  mov     rax, cs:__security_cookie
0x180080f5a  xor     rax, rsp
0x180080f5d  mov     [rbp+57h+var_38], rax
0x180080f61  mov     r9, [rcx+8]
0x180080f65  mov     r12, r8
0x180080f68  mov     rax, r9
0x180080f6b  mov     [rbp+57h+var_80], 0
0x180080f72  sub     rax, [rcx]
0x180080f75  mov     rdi, rdx
0x180080f78  sar     rax, 1
0x180080f7b  mov     r15, rcx
0x180080f7e  jnz     short loc_180080FBE
0x180080f80  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180080f87  mov     [rbp+57h+var_D0], 9Ch
0x180080f8f  mov     [rsp+110h+var_E0], rax
0x180080f94  lea     rax, aCombinepaths; "CombinePaths"
0x180080f9b  mov     [rsp+110h+var_D8], rax
0x180080fa0  lea     rax, aPath1Length0; "Path1.length() > 0"
0x180080fa7  lea     rdx, [rsp+110h+var_E0]
0x180080fac  mov     [rbp+57h+var_C8], rax
0x180080fb0  lea     rcx, [rbp+57h+var_80]
0x180080fb4  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180080fb9  jmp     loc_180081229
0x180080fbe  mov     r8, [rdx]
0x180080fc1  mov     rdx, [rdx+8]
0x180080fc5  sub     rdx, r8
0x180080fc8  sar     rdx, 1
0x180080fcb  jnz     short loc_180080FF6
0x180080fcd  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180080fd4  mov     [rbp+57h+var_D0], 9Dh
0x180080fdc  mov     [rsp+110h+var_E0], rax
0x180080fe1  lea     rax, aCombinepaths; "CombinePaths"
0x180080fe8  mov     [rsp+110h+var_D8], rax
0x180080fed  lea     rax, aPath2Length0; "Path2.length() > 0"
0x180080ff4  jmp     short loc_180080FA7
0x180080ff6  lea     ecx, [rax+2]
0x180080ff9  cmp     ecx, eax
0x180080ffb  jnb     short loc_180081032
0x180080ffd  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180081004  mov     [rbp+57h+var_D0], 0A5h
0x18008100c  mov     [rsp+110h+var_E0], rax
0x180081011  lea     rdx, [rsp+110h+var_E0]
0x180081016  lea     rax, aCombinepaths; "CombinePaths"
0x18008101d  mov     [rsp+110h+var_D8], rax
0x180081022  lea     rax, aUlongaddStatic_0; "ULongAdd( static_cast<ULONG>(Path1.leng"...
0x180081029  mov     [rbp+57h+var_C8], rax
0x18008102d  jmp     loc_18008121A
0x180081032  lea     ebx, [rcx+rdx]
0x180081035  cmp     ebx, edx
0x180081037  jb      loc_1800811ED
0x18008103d  movzx   ecx, word ptr [r9-2]
0x180081042  lea     rax, [rbp+57h+var_48]
0x180081046  movzx   r8d, word ptr [r8]
0x18008104a  xor     r14b, r14b
0x18008104d  mov     [rbp+57h+var_58], rax
0x180081051  lea     rax, [rbp+57h+var_48]
0x180081055  mov     [rbp+57h+var_50], rax
0x180081059  xor     eax, eax
0x18008105b  mov     [rbp+57h+var_48], ax
0x18008105f  cmp     cx, 5Ch ; '\'
0x180081063  jnz     loc_180081196
0x180081069  cmp     r8w, cx
0x18008106d  jnz     loc_18008111E
0x180081073  lea     rcx, [rbp+57h+var_58]
0x180081077  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18008107c  test    al, al
0x18008107e  jnz     short loc_1800810B2
0x180081080  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180081087  mov     [rbp+57h+var_D0], 0B6h
0x18008108f  mov     [rsp+110h+var_E0], rax
0x180081094  lea     rdx, [rsp+110h+var_E0]
0x180081099  lea     rax, aCombinepaths; "CombinePaths"
0x1800810a0  mov     [rsp+110h+var_D8], rax
0x1800810a5  lea     rax, aModifiedpath2R; "ModifiedPath2.resize(Path2.length())"
0x1800810ac  mov     [rbp+57h+var_C8], rax
0x1800810b0  jmp     short loc_180081106
0x1800810b2  mov     r8, [rdi+8]
0x1800810b6  mov     r14d, 1
0x1800810bc  sub     r8, [rdi]
0x1800810bf  mov     r9d, r14d
0x1800810c2  mov     rdx, [rbp+57h+var_58]
0x1800810c6  mov     rcx, rdi
0x1800810c9  sar     r8, 1
0x1800810cc  sub     r8, r14
0x1800810cf  call    ?copy@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_KPEA_W_K1@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::copy(wchar_t *,unsigned __int64,unsigned __int64)
0x1800810d4  test    rax, rax
0x1800810d7  jnz     short loc_18008111C
0x1800810d9  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x1800810e0  mov     [rbp+57h+var_90], 0B7h
0x1800810e8  mov     [rbp+57h+var_A0], rax
0x1800810ec  lea     rdx, [rbp+57h+var_A0]
0x1800810f0  lea     rax, aCombinepaths; "CombinePaths"
0x1800810f7  mov     [rbp+57h+var_98], rax
0x1800810fb  lea     rax, aPath2CopyModif; "Path2.copy(ModifiedPath2.data(), Path2."...
0x180081102  mov     [rbp+57h+var_88], rax
0x180081106  mov     r8d, 0C0000017h
0x18008110c  lea     rcx, [rbp+57h+var_80]
0x180081110  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180081115  mov     ebx, eax
0x180081117  jmp     loc_1800811E0
0x18008111c  dec     ebx
0x18008111e  dec     ebx
0x180081120  lea     rsi, aWsWs; "%ws%ws"
0x180081127  lea     rax, [rbp+57h+var_68]
0x18008112b  mov     rdx, rbx
0x18008112e  mov     [rbp+57h+Buffer], rax
0x180081132  lea     rcx, [rbp+57h+Buffer]
0x180081136  lea     rax, [rbp+57h+var_68]
0x18008113a  mov     [rbp+57h+var_70], rax
0x18008113e  xor     eax, eax
0x180081140  mov     [rbp+57h+var_68], ax
0x180081144  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x180081149  test    al, al
0x18008114b  jnz     short loc_1800811A6
0x18008114d  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180081154  mov     [rbp+57h+var_B0], 0C9h
0x18008115c  mov     [rbp+57h+var_C0], rax
0x180081160  lea     rdx, [rbp+57h+var_C0]
0x180081164  lea     rax, aCombinepaths; "CombinePaths"
0x18008116b  mov     r8d, 0C0000017h
0x180081171  mov     [rbp+57h+var_B8], rax
0x180081175  lea     rcx, [rbp+57h+var_80]
0x180081179  lea     rax, aFullpathResize; "FullPath.resize(PathLength)"
0x180081180  mov     [rbp+57h+var_A8], rax
0x180081184  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180081189  lea     rcx, [rbp+57h+Buffer]
0x18008118d  mov     ebx, eax
0x18008118f  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180081194  jmp     short loc_1800811E0
0x180081196  cmp     r8w, 5Ch ; '\'
0x18008119b  jz      short loc_18008111E
0x18008119d  lea     rsi, aWsWs_0; "%ws\\%ws"
0x1800811a4  jmp     short loc_180081127
0x1800811a6  mov     rax, [rbp+57h+var_58]
0x1800811aa  test    r14b, r14b
0x1800811ad  jnz     short loc_1800811B2
0x1800811af  mov     rax, [rdi]
0x1800811b2  mov     r9, [r15]
0x1800811b5  mov     r8, rsi; Format
0x1800811b8  mov     rcx, [rbp+57h+Buffer]; Buffer
0x1800811bc  mov     rdx, rbx; BufferCount
0x1800811bf  mov     [rsp+110h+var_F0], rax
0x1800811c4  call    swprintf_s
0x1800811c9  lea     rdx, [rbp+57h+Buffer]
0x1800811cd  mov     rcx, r12
0x1800811d0  call    ?swap@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAXAEAV12@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::swap(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800811d5  lea     rcx, [rbp+57h+Buffer]
0x1800811d9  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x1800811de  xor     ebx, ebx
0x1800811e0  lea     rcx, [rbp+57h+var_58]
0x1800811e4  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x1800811e9  mov     eax, ebx
0x1800811eb  jmp     short loc_180081229
0x1800811ed  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x1800811f4  mov     [rbp+57h+var_B0], 0ABh
0x1800811fc  mov     [rbp+57h+var_C0], rax
0x180081200  lea     rdx, [rbp+57h+var_C0]
0x180081204  lea     rax, aCombinepaths; "CombinePaths"
0x18008120b  mov     [rbp+57h+var_B8], rax
0x18008120f  lea     rax, aUlongaddStatic; "ULongAdd( static_cast<ULONG>(Path2.leng"...
0x180081216  mov     [rbp+57h+var_A8], rax
0x18008121a  mov     r8d, 80070216h
0x180081220  lea     rcx, [rbp+57h+var_80]
0x180081224  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180081229  mov     rcx, [rbp+57h+var_38]
0x18008122d  xor     rcx, rsp; StackCookie
0x180081230  call    __security_check_cookie
0x180081235  add     rsp, 0E0h
0x18008123c  pop     r15
0x18008123e  pop     r14
0x180081240  pop     r12
0x180081242  pop     rdi
0x180081243  pop     rsi
0x180081244  pop     rbx
0x180081245  pop     rbp
0x180081246  retn
```
