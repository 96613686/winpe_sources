# Messaging_GetRecipientsPreviewWithBiDiMarkers

- ea: `0x180026280`
- end: `0x1800265e3`
- name: `Messaging_GetRecipientsPreviewWithBiDiMarkers`
- size: `867`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008870`
- `0x18001768c`
- `0x1800176b4`
- `0x180025700`
- `0x180025798`
- `0x180025a20`
- `0x180025a4c`
- `0x180026130`
- `0x180026280`
- `0x1800c50ec`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800263ac`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800263ac`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800263c7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800263c7`

## string_xrefs

- `0x1800263a5`: `MessagingRes.dll`

## pseudocode

```c
__int64 __fastcall Messaging_GetRecipientsPreviewWithBiDiMarkers(int a1, __int64 a2, __int64 *a3, __int64 a4)
{
  int v5; // r15d
  int v6; // r12d
  __int64 v8; // rax
  int v9; // eax
  unsigned int v10; // ebx
  _WORD *v11; // rcx
  int v12; // r14d
  int RecipientsPreviewString; // eax
  HMODULE Library; // rax
  int v15; // eax
  int DirectionalMarkerForCurrentLocale; // eax
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  WCHAR Buffer[4]; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v22; // [rsp+38h] [rbp-51h] BYREF
  __int16 *v23; // [rsp+40h] [rbp-49h] BYREF
  __int16 *v24; // [rsp+48h] [rbp-41h]
  __int16 v25; // [rsp+50h] [rbp-39h] BYREF
  __int64 v26; // [rsp+52h] [rbp-37h]
  int v27; // [rsp+5Ah] [rbp-2Fh]
  __int16 v28; // [rsp+5Eh] [rbp-2Bh]
  __int16 *v29; // [rsp+60h] [rbp-29h] BYREF
  __int16 *v30; // [rsp+68h] [rbp-21h]
  __int16 v31; // [rsp+70h] [rbp-19h] BYREF
  __int64 v32; // [rsp+72h] [rbp-17h]
  int v33; // [rsp+7Ah] [rbp-Fh]
  __int16 v34; // [rsp+7Eh] [rbp-Bh]
  _QWORD v35[2]; // [rsp+80h] [rbp-9h] BYREF
  __int16 v36; // [rsp+90h] [rbp+7h] BYREF
  __int64 v37; // [rsp+92h] [rbp+9h]
  int v38; // [rsp+9Ah] [rbp+11h]
  __int16 v39; // [rsp+9Eh] [rbp+15h]

  v5 = (int)a3;
  v6 = a2;
  if ( a2 && a3 )
  {
    v8 = *a3;
    v22 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v8 + 56))(a3, &v22);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v11 = *(_WORD **)a4;
      *(_QWORD *)(a4 + 8) = *(_QWORD *)a4;
      v12 = 0;
      *v11 = 0;
      if ( !v22 )
        return 0;
      while ( 1 )
      {
        v37 = 0;
        v39 = 0;
        v38 = 0;
        v35[0] = &v36;
        v35[1] = &v36;
        v36 = 0;
        RecipientsPreviewString = GetRecipientsPreviewString(a1, v12, v6, v5, (__int64)v35);
        v10 = RecipientsPreviewString;
        if ( RecipientsPreviewString < 0 )
        {
          v18 = RecipientsPreviewString;
          goto LABEL_32;
        }
        if ( (__int64)(*(_QWORD *)(a4 + 8) - *(_QWORD *)a4) >> 1 )
        {
          if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                   a4,
                                   &dword_1800D7EA4,
                                   1) )
          {
            v10 = -2147024882;
            v18 = -2147024882;
            goto LABEL_32;
          }
          Library = hInstance;
          *(_QWORD *)Buffer = 0;
          if ( !hInstance )
          {
            Library = LoadLibraryExW(L"MessagingRes.dll", 0, 2u);
            hInstance = Library;
          }
          LoadStringW(Library, 0x6Bu, Buffer, 0);
          if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                   a4,
                                   *(_QWORD *)Buffer) )
            break;
        }
        v26 = 0;
        v28 = 0;
        v23 = &v25;
        v24 = &v25;
        v25 = 0;
        v27 = 0;
        v15 = Messaging_FormatStringWithLeftToRightMarkersIfPhoneNumber(v35[0], &v23);
        v10 = v15;
        if ( v15 < 0 )
        {
          v20 = v15;
LABEL_29:
          Log_HREvent_7(v20);
          goto LABEL_30;
        }
        if ( *(_QWORD *)(a4 + 8) == *(_QWORD *)a4 )
        {
          v32 = 0;
          v34 = 0;
          v33 = 0;
          v29 = &v31;
          v30 = &v31;
          v31 = 0;
          DirectionalMarkerForCurrentLocale = GetDirectionalMarkerForCurrentLocale(&v29);
          v10 = DirectionalMarkerForCurrentLocale;
          if ( DirectionalMarkerForCurrentLocale < 0 )
          {
            v19 = DirectionalMarkerForCurrentLocale;
LABEL_25:
            Log_HREvent_7(v19);
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v29);
LABEL_30:
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v23);
            goto LABEL_33;
          }
          if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                   a4,
                                   v29,
                                   v30 - v29) )
          {
            v10 = -2147024882;
            v19 = -2147024882;
            goto LABEL_25;
          }
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v29);
        }
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 a4,
                                 v23,
                                 v24 - v23) )
        {
          v10 = -2147024882;
          v20 = -2147024882;
          goto LABEL_29;
        }
        if ( (unsigned __int64)((__int64)(*(_QWORD *)(a4 + 8) - *(_QWORD *)a4) >> 1) >= 0x96 )
        {
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v23);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v35);
          return 0;
        }
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v23);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v35);
        if ( ++v12 >= v22 )
          return 0;
      }
      v10 = -2147024882;
      Log_HREvent_7(-2147024882);
      v18 = -2147024882;
LABEL_32:
      Log_HREvent_7(v18);
LABEL_33:
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v35);
    }
    else
    {
      Log_HREvent_7(v9);
    }
  }
  else
  {
    v10 = -2147024809;
    Log_HREvent_7(-2147024809);
    Log_AssertionEvent_7();
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  return v10;
}

```

## disassembly

```asm
0x180026280  push    rbp
0x180026282  push    rbx
0x180026283  push    rdi
0x180026284  push    r12
0x180026286  push    r13
0x180026288  push    r14
0x18002628a  push    r15
0x18002628c  lea     rbp, [rsp-27h]
0x180026291  sub     rsp, 0B0h
0x180026298  mov     rax, cs:__security_cookie
0x18002629f  xor     rax, rsp
0x1800262a2  mov     [rbp+57h+var_40], rax
0x1800262a6  mov     rdi, r9
0x1800262a9  mov     r15, r8
0x1800262ac  mov     r12, rdx
0x1800262af  mov     r13, rcx
0x1800262b2  test    rdx, rdx
0x1800262b5  jz      loc_1800265A4
0x1800262bb  test    r8, r8
0x1800262be  jz      loc_1800265A4
0x1800262c4  mov     rax, [r8]
0x1800262c7  lea     rdx, [rbp+57h+var_A8]
0x1800262cb  mov     rcx, r8
0x1800262ce  mov     [rbp+57h+var_A8], 0
0x1800262d5  mov     rax, [rax+38h]
0x1800262d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262de  mov     ebx, eax
0x1800262e0  test    eax, eax
0x1800262e2  jns     short loc_1800262FB
0x1800262e4  mov     edx, 1
0x1800262e9  mov     r9d, 12Bh
0x1800262ef  mov     ecx, eax; int
0x1800262f1  call    Log_HREvent_7
0x1800262f6  jmp     loc_1800265C2
0x1800262fb  mov     rcx, [rdi]
0x1800262fe  xor     eax, eax
0x180026300  mov     [rdi+8], rcx
0x180026304  xor     r14d, r14d
0x180026307  mov     [rcx], ax
0x18002630a  cmp     [rbp+57h+var_A8], eax
0x18002630d  jbe     loc_1800264E4
0x180026313  xor     eax, eax
0x180026315  mov     [rbp+57h+var_4E], 0
0x18002631d  mov     [rbp+57h+var_42], ax
0x180026321  mov     r9, r15
0x180026324  lea     rax, [rbp+57h+var_50]
0x180026328  mov     [rbp+57h+var_46], 0
0x18002632f  mov     [rbp+57h+var_60], rax
0x180026333  mov     r8, r12
0x180026336  lea     rax, [rbp+57h+var_50]
0x18002633a  mov     edx, r14d
0x18002633d  mov     [rbp+57h+var_58], rax
0x180026341  mov     rcx, r13
0x180026344  xor     eax, eax
0x180026346  mov     [rbp+57h+var_50], ax
0x18002634a  lea     rax, [rbp+57h+var_60]
0x18002634e  mov     [rsp+0E0h+var_C0], rax
0x180026353  call    GetRecipientsPreviewString
0x180026358  mov     ebx, eax
0x18002635a  test    eax, eax
0x18002635c  js      loc_180026587
0x180026362  mov     rax, [rdi+8]
0x180026366  sub     rax, [rdi]
0x180026369  sar     rax, 1
0x18002636c  jz      short loc_1800263E1
0x18002636e  mov     r8d, 1
0x180026374  lea     rdx, dword_1800D7EA4
0x18002637b  mov     rcx, rdi
0x18002637e  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180026383  test    al, al
0x180026385  jz      loc_18002650A
0x18002638b  mov     rax, cs:hInstance
0x180026392  mov     qword ptr [rbp+57h+Buffer], 0
0x18002639a  test    rax, rax
0x18002639d  jnz     short loc_1800263B9
0x18002639f  xor     edx, edx; hFile
0x1800263a1  lea     r8d, [rax+2]; dwFlags
0x1800263a5  lea     rcx, aMessagingresDl; "MessagingRes.dll"
0x1800263ac  call    cs:__imp_LoadLibraryExW
0x1800263b2  mov     cs:hInstance, rax
0x1800263b9  xor     r9d, r9d; cchBufferMax
0x1800263bc  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800263c0  mov     rcx, rax; hInstance
0x1800263c3  lea     edx, [r9+6Bh]; uID
0x1800263c7  call    cs:__imp_LoadStringW
0x1800263cd  mov     rdx, qword ptr [rbp+57h+Buffer]
0x1800263d1  mov     rcx, rdi
0x1800263d4  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800263d9  test    al, al
0x1800263db  jz      loc_1800264EB
0x1800263e1  mov     rcx, [rbp+57h+var_60]
0x1800263e5  lea     rdx, [rbp+57h+var_A0]
0x1800263e9  xor     eax, eax
0x1800263eb  mov     [rbp+57h+var_8E], 0
0x1800263f3  mov     [rbp+57h+var_82], ax
0x1800263f7  lea     rax, [rbp+57h+var_90]
0x1800263fb  mov     [rbp+57h+var_A0], rax
0x1800263ff  lea     rax, [rbp+57h+var_90]
0x180026403  mov     [rbp+57h+var_98], rax
0x180026407  xor     eax, eax
0x180026409  mov     [rbp+57h+var_90], ax
0x18002640d  mov     [rbp+57h+var_86], 0
0x180026414  call    Messaging_FormatStringWithLeftToRightMarkersIfPhoneNumber
0x180026419  mov     ebx, eax
0x18002641b  test    eax, eax
0x18002641d  js      loc_18002656A
0x180026423  mov     rax, [rdi+8]
0x180026427  cmp     rax, [rdi]
0x18002642a  jnz     short loc_180026491
0x18002642c  xor     eax, eax
0x18002642e  mov     [rbp+57h+var_6E], 0
0x180026436  mov     [rbp+57h+var_62], ax
0x18002643a  lea     rcx, [rbp+57h+var_80]
0x18002643e  lea     rax, [rbp+57h+var_70]
0x180026442  mov     [rbp+57h+var_66], 0
0x180026449  mov     [rbp+57h+var_80], rax
0x18002644d  lea     rax, [rbp+57h+var_70]
0x180026451  mov     [rbp+57h+var_78], rax
0x180026455  xor     eax, eax
0x180026457  mov     [rbp+57h+var_70], ax
0x18002645b  call    ?GetDirectionalMarkerForCurrentLocale@@YAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GetDirectionalMarkerForCurrentLocale(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180026460  mov     ebx, eax
0x180026462  test    eax, eax
0x180026464  js      loc_18002652C
0x18002646a  mov     r8, [rbp+57h+var_78]
0x18002646e  mov     rcx, rdi
0x180026471  mov     rdx, [rbp+57h+var_80]
0x180026475  sub     r8, rdx
0x180026478  sar     r8, 1
0x18002647b  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180026480  test    al, al
0x180026482  jz      loc_18002651B
0x180026488  lea     rcx, [rbp+57h+var_80]
0x18002648c  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180026491  mov     r8, [rbp+57h+var_98]
0x180026495  mov     rcx, rdi
0x180026498  mov     rdx, [rbp+57h+var_A0]
0x18002649c  sub     r8, rdx
0x18002649f  sar     r8, 1
0x1800264a2  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800264a7  test    al, al
0x1800264a9  jz      loc_180026559
0x1800264af  mov     rax, [rdi+8]
0x1800264b3  lea     rcx, [rbp+57h+var_A0]
0x1800264b7  sub     rax, [rdi]
0x1800264ba  sar     rax, 1
0x1800264bd  cmp     rax, 96h
0x1800264c3  jnb     loc_180026549
0x1800264c9  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800264ce  lea     rcx, [rbp+57h+var_60]
0x1800264d2  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800264d7  inc     r14d
0x1800264da  cmp     r14d, [rbp+57h+var_A8]
0x1800264de  jb      loc_180026313
0x1800264e4  xor     eax, eax
0x1800264e6  jmp     loc_1800265C4
0x1800264eb  xor     edx, edx
0x1800264ed  mov     ebx, 8007000Eh
0x1800264f2  mov     ecx, ebx; int
0x1800264f4  lea     r9d, [rdx+4Fh]
0x1800264f8  call    Log_HREvent_7
0x1800264fd  mov     r9d, 13Ah
0x180026503  mov     ecx, ebx
0x180026505  jmp     loc_18002658F
0x18002650a  mov     ebx, 8007000Eh
0x18002650f  xor     edx, edx
0x180026511  mov     ecx, ebx
0x180026513  mov     r9d, 139h
0x180026519  jmp     short loc_180026594
0x18002651b  mov     ebx, 8007000Eh
0x180026520  xor     edx, edx
0x180026522  mov     ecx, ebx
0x180026524  mov     r9d, 146h
0x18002652a  jmp     short loc_180026539
0x18002652c  mov     edx, 1
0x180026531  mov     r9d, 145h
0x180026537  mov     ecx, eax; int
0x180026539  call    Log_HREvent_7
0x18002653e  lea     rcx, [rbp+57h+var_80]
0x180026542  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180026547  jmp     short loc_18002657C
0x180026549  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18002654e  lea     rcx, [rbp+57h+var_60]
0x180026552  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180026557  jmp     short loc_1800264E4
0x180026559  mov     ebx, 8007000Eh
0x18002655e  xor     edx, edx
0x180026560  mov     ecx, ebx
0x180026562  mov     r9d, 149h
0x180026568  jmp     short loc_180026577
0x18002656a  mov     edx, 1
0x18002656f  mov     r9d, 13Eh
0x180026575  mov     ecx, eax; int
0x180026577  call    Log_HREvent_7
0x18002657c  lea     rcx, [rbp+57h+var_A0]
0x180026580  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180026585  jmp     short loc_180026599
0x180026587  mov     r9d, 134h
0x18002658d  mov     ecx, eax; int
0x18002658f  mov     edx, 1
0x180026594  call    Log_HREvent_7
0x180026599  lea     rcx, [rbp+57h+var_60]
0x18002659d  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800265a2  jmp     short loc_1800265C2
0x1800265a4  mov     ebx, 80070057h
0x1800265a9  xor     edx, edx
0x1800265ab  mov     ecx, ebx; int
0x1800265ad  mov     r9d, 128h
0x1800265b3  call    Log_HREvent_7
0x1800265b8  call    Log_AssertionEvent_7
0x1800265bd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800265c2  mov     eax, ebx
0x1800265c4  mov     rcx, [rbp+57h+var_40]
0x1800265c8  xor     rcx, rsp; StackCookie
0x1800265cb  call    __security_check_cookie
0x1800265d0  add     rsp, 0B0h
0x1800265d7  pop     r15
0x1800265d9  pop     r14
0x1800265db  pop     r13
0x1800265dd  pop     r12
0x1800265df  pop     rdi
0x1800265e0  pop     rbx
0x1800265e1  pop     rbp
0x1800265e2  retn
```
