# Windows::Networking::UX::Internal::WlanNetwork::CompareNetwork(Windows::Networking::UX::IAvailableNetwork *,int *)

- ea: `0x1800586d0`
- end: `0x180058ab2`
- name: `?CompareNetwork@WlanNetwork@Internal@UX@Networking@Windows@@UEAAJPEAUIAvailableNetwork@345@PEAH@Z`
- size: `994`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanNetwork *__hidden this, struct Windows::Networking::UX::IAvailableNetwork *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180008e30`
- `0x1800586d0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800587c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800587d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800587c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800587d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058796`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800587e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058805`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058796`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800587e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058805`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::WlanNetwork::CompareNetwork(
        Windows::Networking::UX::Internal::WlanNetwork *this,
        struct Windows::Networking::UX::IAvailableNetwork *a2,
        int *a3)
{
  int (__fastcall **v3)(_QWORD, _QWORD, _QWORD); // rax
  int v7; // esi
  int v8; // ecx
  int (__fastcall **v9)(_QWORD, _QWORD, _QWORD); // rax
  int v10; // eax
  char v11; // cl
  int (__fastcall **v12)(_QWORD, _QWORD, _QWORD); // rax
  int (__fastcall *v13)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *); // rbx
  HSTRING v14; // rcx
  int (__fastcall **v15)(_QWORD, _QWORD, _QWORD); // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  int (__fastcall **v18)(struct Windows::Networking::UX::IAvailableNetwork *, GUID *, __int64 *); // rax
  int (__fastcall *v19)(struct Windows::Networking::UX::IAvailableNetwork *, GUID *, __int64 *); // rbx
  __int64 v20; // rdx
  __int64 v21; // r8
  int (__fastcall **v22)(_QWORD, _QWORD, _QWORD); // rax
  int (__fastcall **v23)(_QWORD, _QWORD, _QWORD); // rax
  int (__fastcall *v24)(struct Windows::Networking::UX::IAvailableNetwork *, __int64 *); // rbx
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rbx
  int (__fastcall *v28)(__int64, UINT32 *); // rdi
  __int64 v29; // rdx
  __int64 v30; // r8
  UINT32 v31; // eax
  __int64 v32; // rdi
  int (__fastcall *v33)(__int64, HSTRING *); // rbx
  __int64 v34; // rdx
  __int64 v35; // r8
  UINT32 v36; // eax
  __int64 v37; // rdx
  __int64 v38; // r8
  int (__fastcall **v39)(_QWORD, _QWORD, _QWORD); // rax
  __int64 result; // rax
  char v41[4]; // [rsp+20h] [rbp-30h] BYREF
  UINT32 v42; // [rsp+24h] [rbp-2Ch] BYREF
  __int64 v43; // [rsp+28h] [rbp-28h] BYREF
  UINT32 length[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v45; // [rsp+38h] [rbp-18h] BYREF
  HSTRING string; // [rsp+40h] [rbp-10h] BYREF
  int v47; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v48; // [rsp+4Ch] [rbp-4h] BYREF
  char v49; // [rsp+98h] [rbp+48h] BYREF
  char v50; // [rsp+A0h] [rbp+50h] BYREF
  char v51; // [rsp+A8h] [rbp+58h] BYREF

  v3 = *(int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a2;
  v47 = 0;
  v7 = 1;
  if ( ((int (__fastcall *)(struct Windows::Networking::UX::IAvailableNetwork *, int *))v3[12])(a2, &v47) < 0 )
    goto LABEL_8;
  v8 = *((_DWORD *)this - 10);
  if ( (unsigned int)(v8 - 4) > 1 )
  {
LABEL_5:
    if ( v8 != 4 && (unsigned int)(v47 - 4) <= 1 )
      goto LABEL_7;
LABEL_8:
    v9 = *(int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a2;
    v49 = 0;
    v10 = ((__int64 (__fastcall *)(struct Windows::Networking::UX::IAvailableNetwork *, char *))v9[17])(a2, &v49);
    v11 = *((_BYTE *)this - 32);
    if ( v10 < 0 )
    {
      if ( v11 )
        goto LABEL_23;
    }
    else
    {
      if ( v11 )
      {
        if ( !v49 )
          goto LABEL_69;
        goto LABEL_23;
      }
      if ( v49 )
        goto LABEL_7;
    }
    v12 = *(int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a2;
    string = 0;
    v13 = (int (__fastcall *)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *))v12[6];
    WindowsDeleteString(0);
    string = 0;
    if ( v13(a2, &string) >= 0 )
    {
      v14 = (HSTRING)*((_QWORD *)this - 6);
      length[0] = 0;
      v42 = 0;
      WindowsGetStringRawBuffer(v14, length);
      WindowsGetStringRawBuffer(string, &v42);
      if ( length[0] )
      {
        if ( !v42 )
        {
LABEL_18:
          WindowsDeleteString(string);
          goto LABEL_69;
        }
      }
      else if ( v42 )
      {
        v7 = -1;
        goto LABEL_18;
      }
    }
    WindowsDeleteString(string);
LABEL_23:
    v15 = *(int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a2;
    v50 = 0;
    if ( ((int (__fastcall *)(struct Windows::Networking::UX::IAvailableNetwork *, char *))v15[15])(a2, &v50) < 0 )
      goto LABEL_28;
    if ( *((_BYTE *)this - 36) )
    {
      if ( !v50 )
        goto LABEL_69;
LABEL_28:
      v18 = *(int (__fastcall ***)(struct Windows::Networking::UX::IAvailableNetwork *, GUID *, __int64 *))a2;
      v48 = 0;
      v43 = 0;
      v19 = *v18;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43, v16, v17);
      if ( v19(a2, &GUID_ac2798f8_4bd2_4d64_be61_7002641cd494, &v43) >= 0
        && (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v43 + 64LL))(v43, &v48) >= 0 )
      {
        if ( *((_DWORD *)this + 24) > v48 )
        {
LABEL_68:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v43,
            v20,
            v21);
          goto LABEL_69;
        }
        if ( *((_DWORD *)this + 24) < v48 )
          goto LABEL_32;
      }
      v22 = *(int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a2;
      v51 = 0;
      v41[0] = 0;
      if ( ((int (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, char *, char *))v22)[20](
             a2,
             &v51,
             v41) >= 0 )
      {
        if ( *((_BYTE *)this - 35) != v51 )
          goto LABEL_68;
        if ( *((_BYTE *)this - 34) != v41[0] )
        {
LABEL_32:
          v7 = -1;
          goto LABEL_68;
        }
      }
      v23 = *(int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a2;
      v45 = 0;
      v24 = (int (__fastcall *)(struct Windows::Networking::UX::IAvailableNetwork *, __int64 *))v23[21];
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45, v20, v21);
      if ( v24(a2, &v45) >= 0 )
      {
        v27 = v45;
        if ( !v45 )
        {
          if ( !*((_BYTE *)this + 204) )
LABEL_66:
            v7 = 0;
LABEL_67:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v45,
            v25,
            v26);
          goto LABEL_68;
        }
        if ( !*((_BYTE *)this + 204) )
        {
          v7 = -1;
          goto LABEL_67;
        }
        *(_QWORD *)length = 0;
        v28 = *(int (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v45 + 56LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
          length,
          v25,
          v26);
        if ( v28(v27, length) >= 0 )
        {
          if ( *((_BYTE *)this + 196) )
          {
            if ( !*(_QWORD *)length )
              goto LABEL_48;
            v42 = 0;
            if ( (*(int (__fastcall **)(_QWORD, UINT32 *))(**(_QWORD **)length + 48LL))(*(_QWORD *)length, &v42) >= 0 )
            {
              v31 = *((_DWORD *)this + 48);
              if ( v31 > v42 )
                goto LABEL_46;
              if ( v31 < v42 )
              {
LABEL_48:
                v7 = -1;
                goto LABEL_46;
              }
            }
          }
          else if ( *(_QWORD *)length )
          {
LABEL_46:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              length,
              v29,
              v30);
            goto LABEL_67;
          }
        }
        v32 = v45;
        string = 0;
        v33 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v45 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
          &string,
          v29,
          v30);
        if ( v33(v32, &string) >= 0 )
        {
          if ( *((_BYTE *)this + 188) )
          {
            if ( !string )
              goto LABEL_57;
            v42 = 0;
            if ( (*(int (__fastcall **)(HSTRING, UINT32 *))(*(_QWORD *)string + 48LL))(string, &v42) >= 0 )
            {
              v36 = *((_DWORD *)this + 46);
              if ( v36 > v42 )
                goto LABEL_55;
              if ( v36 < v42 )
              {
LABEL_57:
                v7 = -1;
                goto LABEL_55;
              }
            }
          }
          else if ( string )
          {
LABEL_55:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &string,
              v34,
              v35);
            goto LABEL_46;
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
          &string,
          v34,
          v35);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
          length,
          v37,
          v38);
      }
      if ( (unsigned int)(*((_DWORD *)this + 23) - 10) <= 1 )
      {
        v39 = *(int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a2;
        length[0] = 0;
        if ( ((int (__fastcall *)(struct Windows::Networking::UX::IAvailableNetwork *, UINT32 *))v39[18])(a2, length) >= 0
          && length[0] - 10 <= 1
          && length[0] != *((_DWORD *)this + 23) )
        {
          goto LABEL_67;
        }
      }
      goto LABEL_66;
    }
    if ( !v50 )
      goto LABEL_28;
LABEL_7:
    v7 = -1;
    goto LABEL_69;
  }
  if ( (unsigned int)(v47 - 4) <= 1 )
  {
    if ( v8 == 5 )
      goto LABEL_8;
    goto LABEL_5;
  }
LABEL_69:
  result = 0;
  *a3 = v7;
  return result;
}

```

## disassembly

```asm
0x1800586d0  mov     [rsp-38h+arg_0], rbx
0x1800586d5  push    rbp
0x1800586d6  push    rsi
0x1800586d7  push    rdi
0x1800586d8  push    r12
0x1800586da  push    r13
0x1800586dc  push    r14
0x1800586de  push    r15
0x1800586e0  mov     rbp, rsp
0x1800586e3  sub     rsp, 50h
0x1800586e7  mov     rax, [rdx]
0x1800586ea  mov     r15, rdx
0x1800586ed  mov     r14, rcx
0x1800586f0  lea     rdx, [rbp+var_8]
0x1800586f4  xor     r13d, r13d
0x1800586f7  mov     rcx, r15
0x1800586fa  mov     r12, r8
0x1800586fd  mov     [rbp+var_8], r13d
0x180058701  mov     rax, [rax+60h]
0x180058705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005870a  lea     esi, [r13+1]
0x18005870e  test    eax, eax
0x180058710  js      short loc_180058744
0x180058712  mov     ecx, [r14-28h]
0x180058716  mov     edx, [rbp+var_8]
0x180058719  lea     eax, [rcx-4]
0x18005871c  cmp     eax, esi
0x18005871e  ja      short loc_180058730
0x180058720  lea     eax, [rdx-4]
0x180058723  cmp     eax, esi
0x180058725  ja      loc_180058A94
0x18005872b  cmp     ecx, 5
0x18005872e  jz      short loc_180058744
0x180058730  cmp     ecx, 4
0x180058733  jz      short loc_180058744
0x180058735  lea     eax, [rdx-4]
0x180058738  cmp     eax, esi
0x18005873a  ja      short loc_180058744
0x18005873c  or      esi, 0FFFFFFFFh
0x18005873f  jmp     loc_180058A94
0x180058744  mov     rax, [r15]
0x180058747  lea     rdx, [rbp+arg_8]
0x18005874b  mov     rcx, r15
0x18005874e  mov     [rbp+arg_8], r13b
0x180058752  mov     rax, [rax+88h]
0x180058759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005875e  mov     cl, [r14-20h]
0x180058762  test    eax, eax
0x180058764  js      short loc_180058781
0x180058766  test    cl, cl
0x180058768  jz      short loc_180058779
0x18005876a  cmp     [rbp+arg_8], r13b
0x18005876e  jnz     loc_18005880B
0x180058774  jmp     loc_180058A94
0x180058779  cmp     [rbp+arg_8], r13b
0x18005877d  jz      short loc_180058789
0x18005877f  jmp     short loc_18005873C
0x180058781  test    cl, cl
0x180058783  jnz     loc_18005880B
0x180058789  mov     rax, [r15]
0x18005878c  xor     ecx, ecx; string
0x18005878e  mov     [rbp+string], r13
0x180058792  mov     rbx, [rax+30h]
0x180058796  call    cs:__imp_WindowsDeleteString
0x18005879c  lea     rdx, [rbp+string]
0x1800587a0  mov     [rbp+string], r13
0x1800587a4  mov     rcx, r15
0x1800587a7  mov     rax, rbx
0x1800587aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800587af  test    eax, eax
0x1800587b1  js      short loc_180058801
0x1800587b3  mov     rcx, [r14-30h]; string
0x1800587b7  lea     rdx, [rbp+length]; length
0x1800587bb  mov     [rbp+length], r13d
0x1800587bf  mov     [rbp+var_2C], r13d
0x1800587c3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800587c9  mov     rcx, [rbp+string]; string
0x1800587cd  lea     rdx, [rbp+var_2C]; length
0x1800587d1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800587d7  mov     ecx, [rbp+length]
0x1800587da  mov     eax, [rbp+var_2C]
0x1800587dd  test    ecx, ecx
0x1800587df  jz      short loc_1800587F8
0x1800587e1  test    eax, eax
0x1800587e3  jnz     short loc_1800587F4
0x1800587e5  mov     rcx, [rbp+string]; string
0x1800587e9  call    cs:__imp_WindowsDeleteString
0x1800587ef  jmp     loc_180058A94
0x1800587f4  test    ecx, ecx
0x1800587f6  jnz     short loc_180058801
0x1800587f8  test    eax, eax
0x1800587fa  jz      short loc_180058801
0x1800587fc  or      esi, 0FFFFFFFFh
0x1800587ff  jmp     short loc_1800587E5
0x180058801  mov     rcx, [rbp+string]; string
0x180058805  call    cs:__imp_WindowsDeleteString
0x18005880b  mov     rax, [r15]
0x18005880e  lea     rdx, [rbp+arg_10]
0x180058812  mov     rcx, r15
0x180058815  mov     [rbp+arg_10], r13b
0x180058819  mov     rax, [rax+78h]
0x18005881d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058822  test    eax, eax
0x180058824  js      short loc_180058841
0x180058826  cmp     [r14-24h], r13b
0x18005882a  jz      short loc_180058837
0x18005882c  cmp     [rbp+arg_10], r13b
0x180058830  jnz     short loc_180058841
0x180058832  jmp     loc_180058A94
0x180058837  cmp     [rbp+arg_10], r13b
0x18005883b  jnz     loc_18005873C
0x180058841  mov     rax, [r15]
0x180058844  lea     rcx, [rbp+var_28]
0x180058848  mov     [rbp+var_4], r13d
0x18005884c  mov     [rbp+var_28], r13
0x180058850  mov     rbx, [rax]
0x180058853  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058858  lea     r8, [rbp+var_28]
0x18005885c  mov     rcx, r15
0x18005885f  lea     rdx, _GUID_ac2798f8_4bd2_4d64_be61_7002641cd494
0x180058866  mov     rax, rbx
0x180058869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005886e  test    eax, eax
0x180058870  js      short loc_1800588A1
0x180058872  mov     rcx, [rbp+var_28]
0x180058876  lea     rdx, [rbp+var_4]
0x18005887a  mov     rax, [rcx]
0x18005887d  mov     rax, [rax+40h]
0x180058881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058886  test    eax, eax
0x180058888  js      short loc_1800588A1
0x18005888a  mov     eax, [rbp+var_4]
0x18005888d  cmp     [r14+60h], eax
0x180058891  ja      loc_180058A8B
0x180058897  jnb     short loc_1800588A1
0x180058899  or      esi, 0FFFFFFFFh
0x18005889c  jmp     loc_180058A8B
0x1800588a1  mov     rax, [r15]
0x1800588a4  lea     r8, [rbp+var_30]
0x1800588a8  lea     rdx, [rbp+arg_18]
0x1800588ac  mov     [rbp+arg_18], r13b
0x1800588b0  mov     rcx, r15
0x1800588b3  mov     [rbp+var_30], r13b
0x1800588b7  mov     rax, [rax+0A0h]
0x1800588be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800588c3  test    eax, eax
0x1800588c5  js      short loc_1800588DD
0x1800588c7  mov     al, [rbp+arg_18]
0x1800588ca  cmp     [r14-23h], al
0x1800588ce  jnz     loc_180058A8B
0x1800588d4  mov     al, [rbp+var_30]
0x1800588d7  cmp     [r14-22h], al
0x1800588db  jnz     short loc_180058899
0x1800588dd  mov     rax, [r15]
0x1800588e0  lea     rcx, [rbp+var_18]
0x1800588e4  mov     [rbp+var_18], r13
0x1800588e8  mov     rbx, [rax+0A8h]
0x1800588ef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800588f4  lea     rdx, [rbp+var_18]
0x1800588f8  mov     rcx, r15
0x1800588fb  mov     rax, rbx
0x1800588fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058903  test    eax, eax
0x180058905  js      loc_180058A42
0x18005890b  mov     rbx, [rbp+var_18]
0x18005890f  test    rbx, rbx
0x180058912  jnz     short loc_18005892A
0x180058914  lea     rcx, [rbp+var_18]
0x180058918  cmp     [r14+0CCh], r13b
0x18005891f  jnz     loc_180058A86
0x180058925  jmp     loc_180058A83
0x18005892a  cmp     [r14+0CCh], r13b
0x180058931  jnz     short loc_18005893F
0x180058933  or      esi, 0FFFFFFFFh
0x180058936  lea     rcx, [rbp+var_18]
0x18005893a  jmp     loc_180058A86
0x18005893f  mov     qword ptr [rbp+length], r13
0x180058943  lea     rcx, [rbp+length]
0x180058947  mov     rax, [rbx]
0x18005894a  mov     rdi, [rax+38h]
0x18005894e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058953  lea     rdx, [rbp+length]
0x180058957  mov     rcx, rbx
0x18005895a  mov     rax, rdi
0x18005895d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058962  test    eax, eax
0x180058964  js      short loc_1800589B4
0x180058966  cmp     [r14+0C4h], r13b
0x18005896d  jnz     short loc_180058980
0x18005896f  cmp     qword ptr [rbp+length], r13
0x180058973  jz      short loc_1800589B4
0x180058975  lea     rcx, [rbp+length]
0x180058979  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005897e  jmp     short loc_180058936
0x180058980  mov     rcx, qword ptr [rbp+length]
0x180058984  test    rcx, rcx
0x180058987  jnz     short loc_18005898E
0x180058989  or      esi, 0FFFFFFFFh
0x18005898c  jmp     short loc_180058975
0x18005898e  mov     [rbp+var_2C], r13d
0x180058992  lea     rdx, [rbp+var_2C]
0x180058996  mov     rax, [rcx]
0x180058999  mov     rax, [rax+30h]
0x18005899d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800589a2  test    eax, eax
0x1800589a4  js      short loc_1800589B4
0x1800589a6  mov     eax, [r14+0C0h]
0x1800589ad  cmp     eax, [rbp+var_2C]
0x1800589b0  ja      short loc_180058975
0x1800589b2  jb      short loc_180058989
0x1800589b4  mov     rdi, [rbp+var_18]
0x1800589b8  lea     rcx, [rbp+string]
0x1800589bc  mov     [rbp+string], r13
0x1800589c0  mov     rax, [rdi]
0x1800589c3  mov     rbx, [rax+30h]
0x1800589c7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800589cc  lea     rdx, [rbp+string]
0x1800589d0  mov     rcx, rdi
0x1800589d3  mov     rax, rbx
0x1800589d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800589db  test    eax, eax
0x1800589dd  js      short loc_180058A30
0x1800589df  cmp     [r14+0BCh], r13b
0x1800589e6  jnz     short loc_1800589FC
0x1800589e8  cmp     [rbp+string], r13
0x1800589ec  jz      short loc_180058A30
0x1800589ee  lea     rcx, [rbp+string]
0x1800589f2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800589f7  jmp     loc_180058975
0x1800589fc  mov     rcx, [rbp+string]
0x180058a00  test    rcx, rcx
0x180058a03  jnz     short loc_180058A0A
0x180058a05  or      esi, 0FFFFFFFFh
0x180058a08  jmp     short loc_1800589EE
0x180058a0a  mov     [rbp+var_2C], r13d
0x180058a0e  lea     rdx, [rbp+var_2C]
0x180058a12  mov     rax, [rcx]
0x180058a15  mov     rax, [rax+30h]
0x180058a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058a1e  test    eax, eax
0x180058a20  js      short loc_180058A30
0x180058a22  mov     eax, [r14+0B8h]
0x180058a29  cmp     eax, [rbp+var_2C]
0x180058a2c  ja      short loc_1800589EE
0x180058a2e  jb      short loc_180058A05
0x180058a30  lea     rcx, [rbp+string]
0x180058a34  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058a39  lea     rcx, [rbp+length]
0x180058a3d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058a42  mov     eax, [r14+5Ch]
0x180058a46  sub     eax, 0Ah
0x180058a49  cmp     eax, esi
0x180058a4b  ja      short loc_180058A7F
0x180058a4d  mov     rax, [r15]
0x180058a50  lea     rdx, [rbp+length]
0x180058a54  mov     rcx, r15
0x180058a57  mov     [rbp+length], r13d
0x180058a5b  mov     rax, [rax+90h]
0x180058a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058a67  test    eax, eax
0x180058a69  js      short loc_180058A7F
0x180058a6b  mov     ecx, [rbp+length]
0x180058a6e  lea     eax, [rcx-0Ah]
0x180058a71  cmp     eax, esi
0x180058a73  ja      short loc_180058A7F
0x180058a75  cmp     ecx, [r14+5Ch]
0x180058a79  jnz     loc_180058936
0x180058a7f  lea     rcx, [rbp+var_18]
0x180058a83  mov     esi, r13d
0x180058a86  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058a8b  lea     rcx, [rbp+var_28]
0x180058a8f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058a94  mov     rbx, [rsp+50h+arg_0]
0x180058a9c  xor     eax, eax
0x180058a9e  mov     [r12], esi
0x180058aa2  add     rsp, 50h
0x180058aa6  pop     r15
0x180058aa8  pop     r14
0x180058aaa  pop     r13
0x180058aac  pop     r12
0x180058aae  pop     rdi
0x180058aaf  pop     rsi
0x180058ab0  pop     rbp
0x180058ab1  retn
```
