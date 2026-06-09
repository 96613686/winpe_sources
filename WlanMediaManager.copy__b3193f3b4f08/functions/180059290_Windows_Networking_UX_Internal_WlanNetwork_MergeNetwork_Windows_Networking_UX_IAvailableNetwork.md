# Windows::Networking::UX::Internal::WlanNetwork::MergeNetwork(Windows::Networking::UX::IAvailableNetwork *)

- ea: `0x180059290`
- end: `0x180059576`
- name: `?MergeNetwork@WlanNetwork@Internal@UX@Networking@Windows@@UEAAJPEAUIAvailableNetwork@345@@Z`
- size: `742`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanNetwork *__hidden this, struct Windows::Networking::UX::IAvailableNetwork *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180003ed0`
- `0x180008e30`
- `0x18001d4d4`
- `0x18002b930`
- `0x180059290`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059303`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800593ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059303`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800593ec`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::WlanNetwork::MergeNetwork(
        Windows::Networking::UX::Internal::WlanNetwork *this,
        struct Windows::Networking::UX::IAvailableNetwork *a2)
{
  __int64 v2; // rax
  __int64 v5; // rax
  __int64 (__fastcall *v6)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *); // rbx
  int v7; // eax
  __int64 v8; // rax
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  int (__fastcall **v15)(struct Windows::Networking::UX::IAvailableNetwork *, GUID *, __int64 *); // rax
  int (__fastcall *v16)(struct Windows::Networking::UX::IAvailableNetwork *, GUID *, __int64 *); // rbx
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned int v19; // r8d
  __int64 v20; // rcx
  int v21; // r9d
  __int64 i; // rdx
  int v23; // ebx
  __int64 v24; // rcx
  int v25; // ecx
  _BYTE v27[4]; // [rsp+30h] [rbp-39h] BYREF
  unsigned int v28; // [rsp+34h] [rbp-35h] BYREF
  __int64 v29; // [rsp+38h] [rbp-31h] BYREF
  int v30; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v31; // [rsp+44h] [rbp-25h] BYREF
  HSTRING string; // [rsp+48h] [rbp-21h] BYREF
  HSTRING v33; // [rsp+50h] [rbp-19h] BYREF
  _OWORD v34[2]; // [rsp+58h] [rbp-11h]
  int v35; // [rsp+78h] [rbp+Fh]
  int v36; // [rsp+7Ch] [rbp+13h]
  int v37; // [rsp+80h] [rbp+17h]
  _DWORD v38[8]; // [rsp+88h] [rbp+1Fh] BYREF

  v2 = *(_QWORD *)a2;
  v27[0] = 0;
  if ( (*(int (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, _BYTE *))(v2 + 136))(a2, v27) >= 0
    && v27[0]
    && !*((_BYTE *)this - 32) )
  {
    *((_BYTE *)this - 32) = v27[0];
    v5 = *(_QWORD *)a2;
    string = 0;
    v6 = *(__int64 (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *))(v5 + 48);
    WindowsDeleteString(0);
    string = 0;
    v7 = v6(a2, &string);
    if ( v7 >= 0 )
    {
      v33 = string;
      string = 0;
      Microsoft::WRL::Wrappers::HString::Set((HSTRING *)this - 6, &v33);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids,
        (unsigned int)v7);
    }
    v8 = *(_QWORD *)a2;
    v30 = 0;
    if ( (*(int (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, int *))(v8 + 96))(a2, &v30) < 0 )
      goto LABEL_22;
    v9 = *((_DWORD *)this - 10);
    if ( v30 == v9 )
      goto LABEL_22;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( !v10 )
      {
        *((_DWORD *)this - 10) = v30;
        (*(void (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, char *))(*(_QWORD *)a2 + 104LL))(
          a2,
          (char *)this - 16);
        goto LABEL_22;
      }
      v11 = v10 - 1;
      if ( v11 )
      {
        if ( (unsigned int)(v11 - 1) <= 1 && v30 == 5 )
          *((_DWORD *)this - 10) = 5;
        goto LABEL_22;
      }
      if ( (unsigned int)(v30 - 3) > 2 )
      {
LABEL_22:
        WindowsDeleteString(string);
        goto LABEL_23;
      }
    }
    else if ( v30 == 1 )
    {
      goto LABEL_22;
    }
    *((_DWORD *)this - 10) = v30;
    goto LABEL_22;
  }
LABEL_23:
  v12 = *(_QWORD *)a2;
  v31 = 0;
  if ( (*(int (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, unsigned int *))(v12 + 80))(a2, &v31) >= 0
    && v31 > *((_DWORD *)this - 7) )
  {
    *((_DWORD *)this - 7) = v31;
  }
  v15 = *(int (__fastcall ***)(struct Windows::Networking::UX::IAvailableNetwork *, GUID *, __int64 *))a2;
  v28 = 0;
  v29 = 0;
  v16 = *v15;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29, v13, v14);
  if ( v16(a2, &GUID_ac2798f8_4bd2_4d64_be61_7002641cd494, &v29) >= 0 )
  {
    if ( (*(int (__fastcall **)(__int64, __int64, _DWORD *, unsigned int *))(*(_QWORD *)v29 + 72LL))(v29, 8, v38, &v28) >= 0 )
    {
      v19 = v28;
      if ( v28 )
      {
        v20 = 0;
        do
        {
          v21 = v38[v20];
          for ( i = 0; (unsigned int)i < *((_DWORD *)this + 27); i = (unsigned int)(i + 1) )
          {
            if ( *((_DWORD *)this + i + 29) == v21 )
              goto LABEL_36;
          }
          if ( *((_DWORD *)this + 27) < 8u )
          {
            *((_DWORD *)this + (unsigned int)(*((_DWORD *)this + 27))++ + 29) = v21;
            v19 = v28;
          }
LABEL_36:
          v20 = (unsigned int)(v20 + 1);
        }
        while ( (unsigned int)v20 < v19 );
      }
    }
    v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 88LL))(v29);
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v29 + 144LL))(v29) )
    {
      if ( *((_DWORD *)this - 4) == 1 )
      {
        v24 = v29;
        *((_DWORD *)this + 25) = v23;
        *((_DWORD *)this + 26) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 96LL))(v24);
      }
      else
      {
        v17 = 0;
        v34[0] = _mm_load_si128((const __m128i *)&_xmm);
        v35 = 10;
        v34[1] = _mm_load_si128((const __m128i *)&_xmm);
        v36 = 1;
        v37 = 2;
        while ( (unsigned int)v17 < 0xB )
        {
          v25 = *((_DWORD *)v34 + (int)v17);
          if ( *((_DWORD *)this + 25) == v25 || v23 == v25 )
            goto LABEL_46;
          v17 = (unsigned int)(v17 + 1);
        }
        v25 = v23;
LABEL_46:
        *((_DWORD *)this + 25) = v25;
      }
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29, v17, v18);
  return 0;
}

```

## disassembly

```asm
0x180059290  mov     [rsp-8+arg_10], rbx
0x180059295  push    rbp
0x180059296  push    rsi
0x180059297  push    rdi
0x180059298  lea     rbp, [rsp-47h]
0x18005929d  sub     rsp, 0B0h
0x1800592a4  mov     rax, cs:__security_cookie
0x1800592ab  xor     rax, rsp
0x1800592ae  mov     [rbp+57h+var_18], rax
0x1800592b2  mov     rax, [rdx]
0x1800592b5  mov     rsi, rdx
0x1800592b8  mov     rdi, rcx
0x1800592bb  mov     [rbp+57h+var_90], 0
0x1800592bf  lea     rdx, [rbp+57h+var_90]
0x1800592c3  mov     rcx, rsi
0x1800592c6  mov     rax, [rax+88h]
0x1800592cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800592d2  test    eax, eax
0x1800592d4  js      loc_1800593F2
0x1800592da  mov     al, [rbp+57h+var_90]
0x1800592dd  test    al, al
0x1800592df  jz      loc_1800593F2
0x1800592e5  cmp     byte ptr [rdi-20h], 0
0x1800592e9  jnz     loc_1800593F2
0x1800592ef  mov     [rdi-20h], al
0x1800592f2  xor     ecx, ecx; string
0x1800592f4  mov     rax, [rsi]
0x1800592f7  mov     [rbp+57h+string], 0
0x1800592ff  mov     rbx, [rax+30h]
0x180059303  call    cs:__imp_WindowsDeleteString
0x180059309  lea     rdx, [rbp+57h+string]
0x18005930d  mov     [rbp+57h+string], 0
0x180059315  mov     rcx, rsi
0x180059318  mov     rax, rbx
0x18005931b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059320  test    eax, eax
0x180059322  jns     short loc_180059357
0x180059324  mov     rcx, cs:WPP_GLOBAL_Control
0x18005932b  lea     rdx, WPP_GLOBAL_Control
0x180059332  cmp     rcx, rdx
0x180059335  jz      short loc_180059374
0x180059337  test    byte ptr [rcx+1Ch], 2
0x18005933b  jz      short loc_180059374
0x18005933d  mov     rcx, [rcx+10h]
0x180059341  lea     r8, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids
0x180059348  mov     edx, 0Ah
0x18005934d  mov     r9d, eax
0x180059350  call    WPP_SF_d
0x180059355  jmp     short loc_180059374
0x180059357  mov     rax, [rbp+57h+string]
0x18005935b  lea     rcx, [rdi-30h]; newString
0x18005935f  lea     rdx, [rbp+57h+var_70]; HSTRING *
0x180059363  mov     [rbp+57h+var_70], rax
0x180059367  mov     [rbp+57h+string], 0
0x18005936f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180059374  mov     rax, [rsi]
0x180059377  lea     rdx, [rbp+57h+var_80]
0x18005937b  mov     rcx, rsi
0x18005937e  mov     [rbp+57h+var_80], 0
0x180059385  mov     rax, [rax+60h]
0x180059389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005938e  test    eax, eax
0x180059390  js      short loc_1800593E8
0x180059392  mov     ecx, [rdi-28h]
0x180059395  mov     edx, [rbp+57h+var_80]
0x180059398  cmp     edx, ecx
0x18005939a  jz      short loc_1800593E8
0x18005939c  test    ecx, ecx
0x18005939e  jz      short loc_1800593E0
0x1800593a0  sub     ecx, 1
0x1800593a3  jz      short loc_1800593C8
0x1800593a5  sub     ecx, 1
0x1800593a8  jz      short loc_1800593BE
0x1800593aa  sub     ecx, 1
0x1800593ad  jz      short loc_1800593B4
0x1800593af  cmp     ecx, 1
0x1800593b2  jnz     short loc_1800593E8
0x1800593b4  cmp     edx, 5
0x1800593b7  jnz     short loc_1800593E8
0x1800593b9  mov     [rdi-28h], edx
0x1800593bc  jmp     short loc_1800593E8
0x1800593be  lea     eax, [rdx-3]
0x1800593c1  cmp     eax, 2
0x1800593c4  jbe     short loc_1800593E5
0x1800593c6  jmp     short loc_1800593E8
0x1800593c8  mov     [rdi-28h], edx
0x1800593cb  mov     rcx, rsi
0x1800593ce  mov     rax, [rsi]
0x1800593d1  lea     rdx, [rdi-10h]
0x1800593d5  mov     rax, [rax+68h]
0x1800593d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800593de  jmp     short loc_1800593E8
0x1800593e0  cmp     edx, 1
0x1800593e3  jz      short loc_1800593E8
0x1800593e5  mov     [rdi-28h], edx
0x1800593e8  mov     rcx, [rbp+57h+string]; string
0x1800593ec  call    cs:__imp_WindowsDeleteString
0x1800593f2  mov     rax, [rsi]
0x1800593f5  lea     rdx, [rbp+57h+var_7C]
0x1800593f9  mov     rcx, rsi
0x1800593fc  mov     [rbp+57h+var_7C], 0
0x180059403  mov     rax, [rax+50h]
0x180059407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005940c  test    eax, eax
0x18005940e  js      short loc_18005941B
0x180059410  mov     eax, [rbp+57h+var_7C]
0x180059413  cmp     eax, [rdi-1Ch]
0x180059416  jbe     short loc_18005941B
0x180059418  mov     [rdi-1Ch], eax
0x18005941b  mov     rax, [rsi]
0x18005941e  lea     rcx, [rbp+57h+var_88]
0x180059422  mov     [rbp+57h+var_8C], 0
0x180059429  mov     [rbp+57h+var_88], 0
0x180059431  mov     rbx, [rax]
0x180059434  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180059439  lea     r8, [rbp+57h+var_88]
0x18005943d  mov     rcx, rsi
0x180059440  lea     rdx, _GUID_ac2798f8_4bd2_4d64_be61_7002641cd494
0x180059447  mov     rax, rbx
0x18005944a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005944f  test    eax, eax
0x180059451  js      loc_18005954C
0x180059457  mov     rcx, [rbp+57h+var_88]
0x18005945b  lea     r9, [rbp+57h+var_8C]
0x18005945f  lea     r8, [rbp+57h+var_38]
0x180059463  mov     edx, 8
0x180059468  mov     rax, [rcx]
0x18005946b  mov     rax, [rax+48h]
0x18005946f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059474  test    eax, eax
0x180059476  js      short loc_1800594B6
0x180059478  mov     r8d, [rbp+57h+var_8C]
0x18005947c  test    r8d, r8d
0x18005947f  jz      short loc_1800594B6
0x180059481  xor     ecx, ecx
0x180059483  mov     r9d, [rbp+rcx*4+57h+var_38]
0x180059488  xor     edx, edx
0x18005948a  cmp     edx, [rdi+6Ch]
0x18005948d  jnb     short loc_18005949A
0x18005948f  cmp     [rdi+rdx*4+74h], r9d
0x180059494  jz      short loc_1800594AF
0x180059496  inc     edx
0x180059498  jmp     short loc_18005948A
0x18005949a  cmp     dword ptr [rdi+6Ch], 8
0x18005949e  jnb     short loc_1800594AF
0x1800594a0  mov     eax, [rdi+6Ch]
0x1800594a3  mov     [rdi+rax*4+74h], r9d
0x1800594a8  inc     dword ptr [rdi+6Ch]
0x1800594ab  mov     r8d, [rbp+57h+var_8C]
0x1800594af  inc     ecx
0x1800594b1  cmp     ecx, r8d
0x1800594b4  jb      short loc_180059483
0x1800594b6  mov     rcx, [rbp+57h+var_88]
0x1800594ba  mov     rax, [rcx]
0x1800594bd  mov     rax, [rax+58h]
0x1800594c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594c6  mov     rcx, [rbp+57h+var_88]
0x1800594ca  mov     ebx, eax
0x1800594cc  mov     rdx, [rcx]
0x1800594cf  mov     rax, [rdx+90h]
0x1800594d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594db  test    al, al
0x1800594dd  jnz     short loc_18005954C
0x1800594df  cmp     dword ptr [rdi-10h], 1
0x1800594e3  jnz     short loc_1800594FD
0x1800594e5  mov     rcx, [rbp+57h+var_88]
0x1800594e9  mov     [rdi+64h], ebx
0x1800594ec  mov     rax, [rcx]
0x1800594ef  mov     rax, [rax+60h]
0x1800594f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594f8  mov     [rdi+68h], eax
0x1800594fb  jmp     short loc_18005954C
0x1800594fd  movdqa  xmm0, cs:__xmm@00000003000000060000000b00000008
0x180059505  xor     edx, edx
0x180059507  movdqa  xmm1, cs:__xmm@00000005000000040000000700000009
0x18005950f  movdqu  [rbp+57h+var_68], xmm0
0x180059514  mov     [rbp+57h+var_48], 0Ah
0x18005951b  movdqu  [rbp+57h+var_58], xmm1
0x180059520  mov     [rbp+57h+var_44], 1
0x180059527  mov     [rbp+57h+var_40], 2
0x18005952e  cmp     edx, 0Bh
0x180059531  jnb     short loc_180059547
0x180059533  movsxd  rax, edx
0x180059536  mov     ecx, dword ptr [rbp+rax*4+57h+var_68]
0x18005953a  cmp     [rdi+64h], ecx
0x18005953d  jz      short loc_180059549
0x18005953f  cmp     ebx, ecx
0x180059541  jz      short loc_180059549
0x180059543  inc     edx
0x180059545  jmp     short loc_18005952E
0x180059547  mov     ecx, ebx
0x180059549  mov     [rdi+64h], ecx
0x18005954c  lea     rcx, [rbp+57h+var_88]
0x180059550  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180059555  xor     eax, eax
0x180059557  mov     rcx, [rbp+57h+var_18]
0x18005955b  xor     rcx, rsp; StackCookie
0x18005955e  call    __security_check_cookie
0x180059563  mov     rbx, [rsp+0C0h+arg_10]
0x18005956b  add     rsp, 0B0h
0x180059572  pop     rdi
0x180059573  pop     rsi
0x180059574  pop     rbp
0x180059575  retn
```
