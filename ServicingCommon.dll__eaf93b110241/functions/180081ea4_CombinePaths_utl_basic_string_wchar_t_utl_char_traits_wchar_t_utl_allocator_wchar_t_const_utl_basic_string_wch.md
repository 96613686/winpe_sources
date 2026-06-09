# CombinePaths(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x180081ea4`
- end: `0x1800821b0`
- name: `?CombinePaths@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0AEAV12@@Z`
- size: `780`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18007e3f4`
- `0x18007e534`
- `0x18007f370`
- `0x18007faa0`
- `0x180082ccc`

## callees

- `0x18001f4ac`
- `0x18001f5d4`
- `0x1800293a0`
- `0x18002cc98`
- `0x18007ef14`
- `0x18007f0e8`
- `0x18007f214`
- `0x18007f2b4`
- `0x180081ea4`

## string_xrefs

- `0x180081efc`: `CombinePaths`
- `0x180081f49`: `CombinePaths`
- `0x180081f7e`: `CombinePaths`
- `0x180082001`: `CombinePaths`
- `0x180082058`: `CombinePaths`
- `0x1800820cc`: `CombinePaths`
- `0x18008216c`: `CombinePaths`
- `0x180081ee8`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180081f35`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180081f65`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180081fe8`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082041`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800820b5`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082155`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180081f55`: `Path2.length() > 0`
- `0x180081f08`: `Path1.length() > 0`
- `0x180082177`: `ULongAdd( static_cast<ULONG>(Path2.length()), PathLength, &PathLength)`
- `0x180081f8a`: `ULongAdd( static_cast<ULONG>(Path1.length()), PathLength, &PathLength)`
- `0x180082063`: `Path2.copy(ModifiedPath2.data(), Path2.length() - 1, 1)`
- `0x18008200d`: `ModifiedPath2.resize(Path2.length())`
- `0x1800820e1`: `FullPath.resize(PathLength)`

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
0x180081ea4  push    rbp
0x180081ea6  push    rbx
0x180081ea7  push    rsi
0x180081ea8  push    rdi
0x180081ea9  push    r12
0x180081eab  push    r14
0x180081ead  push    r15
0x180081eaf  lea     rbp, [rsp-27h]
0x180081eb4  sub     rsp, 0E0h
0x180081ebb  mov     rax, cs:__security_cookie
0x180081ec2  xor     rax, rsp
0x180081ec5  mov     [rbp+57h+var_38], rax
0x180081ec9  mov     r9, [rcx+8]
0x180081ecd  mov     r12, r8
0x180081ed0  mov     rax, r9
0x180081ed3  mov     [rbp+57h+var_80], 0
0x180081eda  sub     rax, [rcx]
0x180081edd  mov     rdi, rdx
0x180081ee0  sar     rax, 1
0x180081ee3  mov     r15, rcx
0x180081ee6  jnz     short loc_180081F26
0x180081ee8  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180081eef  mov     [rbp+57h+var_D0], 9Ch
0x180081ef7  mov     [rsp+110h+var_E0], rax
0x180081efc  lea     rax, aCombinepaths; "CombinePaths"
0x180081f03  mov     [rsp+110h+var_D8], rax
0x180081f08  lea     rax, aPath1Length0; "Path1.length() > 0"
0x180081f0f  lea     rdx, [rsp+110h+var_E0]
0x180081f14  mov     [rbp+57h+var_C8], rax
0x180081f18  lea     rcx, [rbp+57h+var_80]
0x180081f1c  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180081f21  jmp     loc_180082191
0x180081f26  mov     r8, [rdx]
0x180081f29  mov     rdx, [rdx+8]
0x180081f2d  sub     rdx, r8
0x180081f30  sar     rdx, 1
0x180081f33  jnz     short loc_180081F5E
0x180081f35  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180081f3c  mov     [rbp+57h+var_D0], 9Dh
0x180081f44  mov     [rsp+110h+var_E0], rax
0x180081f49  lea     rax, aCombinepaths; "CombinePaths"
0x180081f50  mov     [rsp+110h+var_D8], rax
0x180081f55  lea     rax, aPath2Length0; "Path2.length() > 0"
0x180081f5c  jmp     short loc_180081F0F
0x180081f5e  lea     ecx, [rax+2]
0x180081f61  cmp     ecx, eax
0x180081f63  jnb     short loc_180081F9A
0x180081f65  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180081f6c  mov     [rbp+57h+var_D0], 0A5h
0x180081f74  mov     [rsp+110h+var_E0], rax
0x180081f79  lea     rdx, [rsp+110h+var_E0]
0x180081f7e  lea     rax, aCombinepaths; "CombinePaths"
0x180081f85  mov     [rsp+110h+var_D8], rax
0x180081f8a  lea     rax, aUlongaddStatic_0; "ULongAdd( static_cast<ULONG>(Path1.leng"...
0x180081f91  mov     [rbp+57h+var_C8], rax
0x180081f95  jmp     loc_180082182
0x180081f9a  lea     ebx, [rcx+rdx]
0x180081f9d  cmp     ebx, edx
0x180081f9f  jb      loc_180082155
0x180081fa5  movzx   ecx, word ptr [r9-2]
0x180081faa  lea     rax, [rbp+57h+var_48]
0x180081fae  movzx   r8d, word ptr [r8]
0x180081fb2  xor     r14b, r14b
0x180081fb5  mov     [rbp+57h+var_58], rax
0x180081fb9  lea     rax, [rbp+57h+var_48]
0x180081fbd  mov     [rbp+57h+var_50], rax
0x180081fc1  xor     eax, eax
0x180081fc3  mov     [rbp+57h+var_48], ax
0x180081fc7  cmp     cx, 5Ch ; '\'
0x180081fcb  jnz     loc_1800820FE
0x180081fd1  cmp     r8w, cx
0x180081fd5  jnz     loc_180082086
0x180081fdb  lea     rcx, [rbp+57h+var_58]
0x180081fdf  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x180081fe4  test    al, al
0x180081fe6  jnz     short loc_18008201A
0x180081fe8  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180081fef  mov     [rbp+57h+var_D0], 0B6h
0x180081ff7  mov     [rsp+110h+var_E0], rax
0x180081ffc  lea     rdx, [rsp+110h+var_E0]
0x180082001  lea     rax, aCombinepaths; "CombinePaths"
0x180082008  mov     [rsp+110h+var_D8], rax
0x18008200d  lea     rax, aModifiedpath2R; "ModifiedPath2.resize(Path2.length())"
0x180082014  mov     [rbp+57h+var_C8], rax
0x180082018  jmp     short loc_18008206E
0x18008201a  mov     r8, [rdi+8]
0x18008201e  mov     r14d, 1
0x180082024  sub     r8, [rdi]
0x180082027  mov     r9d, r14d
0x18008202a  mov     rdx, [rbp+57h+var_58]
0x18008202e  mov     rcx, rdi
0x180082031  sar     r8, 1
0x180082034  sub     r8, r14
0x180082037  call    ?copy@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_KPEA_W_K1@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::copy(wchar_t *,unsigned __int64,unsigned __int64)
0x18008203c  test    rax, rax
0x18008203f  jnz     short loc_180082084
0x180082041  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180082048  mov     [rbp+57h+var_90], 0B7h
0x180082050  mov     [rbp+57h+var_A0], rax
0x180082054  lea     rdx, [rbp+57h+var_A0]
0x180082058  lea     rax, aCombinepaths; "CombinePaths"
0x18008205f  mov     [rbp+57h+var_98], rax
0x180082063  lea     rax, aPath2CopyModif; "Path2.copy(ModifiedPath2.data(), Path2."...
0x18008206a  mov     [rbp+57h+var_88], rax
0x18008206e  mov     r8d, 0C0000017h
0x180082074  lea     rcx, [rbp+57h+var_80]
0x180082078  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18008207d  mov     ebx, eax
0x18008207f  jmp     loc_180082148
0x180082084  dec     ebx
0x180082086  dec     ebx
0x180082088  lea     rsi, aWsWs; "%ws%ws"
0x18008208f  lea     rax, [rbp+57h+var_68]
0x180082093  mov     rdx, rbx
0x180082096  mov     [rbp+57h+Buffer], rax
0x18008209a  lea     rcx, [rbp+57h+Buffer]
0x18008209e  lea     rax, [rbp+57h+var_68]
0x1800820a2  mov     [rbp+57h+var_70], rax
0x1800820a6  xor     eax, eax
0x1800820a8  mov     [rbp+57h+var_68], ax
0x1800820ac  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x1800820b1  test    al, al
0x1800820b3  jnz     short loc_18008210E
0x1800820b5  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x1800820bc  mov     [rbp+57h+var_B0], 0C9h
0x1800820c4  mov     [rbp+57h+var_C0], rax
0x1800820c8  lea     rdx, [rbp+57h+var_C0]
0x1800820cc  lea     rax, aCombinepaths; "CombinePaths"
0x1800820d3  mov     r8d, 0C0000017h
0x1800820d9  mov     [rbp+57h+var_B8], rax
0x1800820dd  lea     rcx, [rbp+57h+var_80]
0x1800820e1  lea     rax, aFullpathResize; "FullPath.resize(PathLength)"
0x1800820e8  mov     [rbp+57h+var_A8], rax
0x1800820ec  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800820f1  lea     rcx, [rbp+57h+Buffer]
0x1800820f5  mov     ebx, eax
0x1800820f7  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x1800820fc  jmp     short loc_180082148
0x1800820fe  cmp     r8w, 5Ch ; '\'
0x180082103  jz      short loc_180082086
0x180082105  lea     rsi, aWsWs_0; "%ws\\%ws"
0x18008210c  jmp     short loc_18008208F
0x18008210e  mov     rax, [rbp+57h+var_58]
0x180082112  test    r14b, r14b
0x180082115  jnz     short loc_18008211A
0x180082117  mov     rax, [rdi]
0x18008211a  mov     r9, [r15]
0x18008211d  mov     r8, rsi; Format
0x180082120  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180082124  mov     rdx, rbx; BufferCount
0x180082127  mov     [rsp+110h+var_F0], rax
0x18008212c  call    swprintf_s
0x180082131  lea     rdx, [rbp+57h+Buffer]
0x180082135  mov     rcx, r12
0x180082138  call    ?swap@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAXAEAV12@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::swap(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18008213d  lea     rcx, [rbp+57h+Buffer]
0x180082141  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180082146  xor     ebx, ebx
0x180082148  lea     rcx, [rbp+57h+var_58]
0x18008214c  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180082151  mov     eax, ebx
0x180082153  jmp     short loc_180082191
0x180082155  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x18008215c  mov     [rbp+57h+var_B0], 0ABh
0x180082164  mov     [rbp+57h+var_C0], rax
0x180082168  lea     rdx, [rbp+57h+var_C0]
0x18008216c  lea     rax, aCombinepaths; "CombinePaths"
0x180082173  mov     [rbp+57h+var_B8], rax
0x180082177  lea     rax, aUlongaddStatic; "ULongAdd( static_cast<ULONG>(Path2.leng"...
0x18008217e  mov     [rbp+57h+var_A8], rax
0x180082182  mov     r8d, 80070216h
0x180082188  lea     rcx, [rbp+57h+var_80]
0x18008218c  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180082191  mov     rcx, [rbp+57h+var_38]
0x180082195  xor     rcx, rsp; StackCookie
0x180082198  call    __security_check_cookie
0x18008219d  add     rsp, 0E0h
0x1800821a4  pop     r15
0x1800821a6  pop     r14
0x1800821a8  pop     r12
0x1800821aa  pop     rdi
0x1800821ab  pop     rsi
0x1800821ac  pop     rbx
0x1800821ad  pop     rbp
0x1800821ae  retn
```
