# AuthHostWebInstance::IsSilentLogonZoneForUrl(ushort const *)

- ea: `0x1400104f0`
- end: `0x1400107c2`
- name: `?IsSilentLogonZoneForUrl@AuthHostWebInstance@@AEAAHPEBG@Z`
- size: `722`
- prototype: `int(AuthHostWebInstance *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140010900`

## callees

- `0x140003a8c`
- `0x14000cd18`
- `0x14000cddc`
- `0x1400104f0`
- `0x140011694`
- `0x140014010`

## import_xrefs

- `urlmon!CreateUri` at `0x140010545`
- `urlmon!CreateUri` at `0x140010545`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AuthHostWebInstance::IsSilentLogonZoneForUrl(AuthHostWebInstance *this, const unsigned __int16 *a2)
{
  unsigned int v4; // r14d
  HRESULT v5; // eax
  _QWORD *v6; // rcx
  int v7; // edx
  int v8; // ecx
  const wchar_t *v9; // rdi
  const wchar_t *v10; // r9
  int v12; // [rsp+88h] [rbp+10h] BYREF
  IUri *ppURI; // [rsp+90h] [rbp+18h] BYREF

  v4 = 0;
  v12 = -1;
  ppURI = 0;
  if ( !a2 || !*((_QWORD *)this + 11) )
    goto LABEL_46;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppURI);
  v5 = CreateUri(a2, 0x2000u, 0, &ppURI);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, IUri *, int *, __int64, _QWORD, _QWORD, _DWORD, _QWORD))(**((_QWORD **)this + 11) + 24LL))(
           *((_QWORD *)this + 11),
           ppURI,
           &v12,
           1,
           0,
           0,
           0,
           0);
    if ( v5 >= 0 )
    {
      v8 = v12;
      v9 = (const wchar_t *)L"Unexpected";
      if ( ((v12 - 1) & 0xFFFFFFFD) != 0 )
      {
        if ( v12 )
        {
          if ( v12 == 2 )
          {
            v10 = L"Trusted";
          }
          else
          {
            v10 = (const wchar_t *)L"Unexpected";
            if ( v12 == 4 )
              v10 = L"Untrusted";
          }
        }
        else
        {
          v10 = L"LocalMachine";
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
        {
          WPP_SF_SdS(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            17,
            (unsigned int)&WPP_2f62e1cc15cd35a2451044e3f3cd4e75_Traceguids,
            (_DWORD)v10,
            v12,
            (__int64)a2);
        }
        v5 = (*(__int64 (__fastcall **)(_QWORD, IUri *, int *, __int64, _QWORD, _QWORD, _DWORD, _QWORD))(**((_QWORD **)this + 11) + 24LL))(
               *((_QWORD *)this + 11),
               ppURI,
               &v12,
               20481,
               0,
               0,
               0,
               0);
        if ( v5 < 0 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
          {
            v7 = 18;
            goto LABEL_8;
          }
          goto LABEL_46;
        }
        v8 = v12;
      }
      if ( v8 )
      {
        switch ( v8 )
        {
          case 1:
            v9 = L"Intranet";
            v4 = 1;
            break;
          case 2:
            v9 = L"Trusted";
            break;
          case 3:
            v9 = L"Internet";
            break;
          case 4:
            v9 = L"Untrusted";
            break;
        }
      }
      else
      {
        v9 = L"LocalMachine";
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
      {
        WPP_SF_dSdS(*((_QWORD *)WPP_GLOBAL_Control + 7), (__int64)v9, v8, (__int64)a2);
      }
      goto LABEL_46;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v7 = 16;
      goto LABEL_8;
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v7 = 15;
LABEL_8:
      WPP_SF_dS(v6[7], v7, (unsigned int)&WPP_2f62e1cc15cd35a2451044e3f3cd4e75_Traceguids, v5, (__int64)a2);
    }
  }
LABEL_46:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppURI);
  return v4;
}

```

## disassembly

```asm
0x1400104f0  mov     rax, rsp
0x1400104f3  mov     [rax+8], rbx
0x1400104f7  push    rbp
0x1400104f8  push    rsi
0x1400104f9  push    rdi
0x1400104fa  push    r12
0x1400104fc  push    r14
0x1400104fe  sub     rsp, 50h
0x140010502  mov     rsi, rdx
0x140010505  mov     rbp, rcx
0x140010508  xor     r14d, r14d
0x14001050b  mov     dword ptr [rax+10h], 0FFFFFFFFh
0x140010512  mov     [rax+18h], r14
0x140010516  test    rdx, rdx
0x140010519  jz      loc_14001079E
0x14001051f  cmp     [rcx+58h], r14
0x140010523  jz      loc_14001079E
0x140010529  lea     rcx, [rax+18h]
0x14001052d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140010532  lea     r9, [rsp+78h+ppURI]; ppURI
0x14001053a  xor     r8d, r8d; dwReserved
0x14001053d  mov     edx, 2000h; dwFlags
0x140010542  mov     rcx, rsi; pwzURI
0x140010545  call    cs:__imp_CreateUri
0x14001054b  test    eax, eax
0x14001054d  jns     short loc_14001059B
0x14001054f  lea     rbx, WPP_GLOBAL_Control
0x140010556  mov     rcx, cs:WPP_GLOBAL_Control
0x14001055d  cmp     rcx, rbx
0x140010560  jz      loc_14001079E
0x140010566  test    byte ptr [rcx+44h], 20h
0x14001056a  jz      loc_14001079E
0x140010570  cmp     byte ptr [rcx+41h], 2
0x140010574  jb      loc_14001079E
0x14001057a  lea     edx, [r14+0Fh]
0x14001057e  mov     [rsp+78h+var_58], rsi
0x140010583  mov     r9d, eax
0x140010586  lea     r8, WPP_2f62e1cc15cd35a2451044e3f3cd4e75_Traceguids
0x14001058d  mov     rcx, [rcx+38h]
0x140010591  call    WPP_SF_dS
0x140010596  jmp     loc_14001079E
0x14001059b  mov     rcx, [rbp+58h]
0x14001059f  mov     rax, [rcx]
0x1400105a2  mov     [rsp+78h+var_40], 0
0x1400105ab  mov     dword ptr [rsp+78h+var_48], 0
0x1400105b3  mov     qword ptr [rsp+78h+var_50], 0
0x1400105bc  mov     [rsp+78h+var_58], 0
0x1400105c5  mov     r9d, 1
0x1400105cb  lea     r8, [rsp+78h+arg_8]
0x1400105d3  mov     rdx, [rsp+78h+ppURI]
0x1400105db  mov     rax, [rax+18h]
0x1400105df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400105e4  test    eax, eax
0x1400105e6  jns     short loc_14001061D
0x1400105e8  lea     rbx, WPP_GLOBAL_Control
0x1400105ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400105f6  cmp     rcx, rbx
0x1400105f9  jz      loc_14001079E
0x1400105ff  test    byte ptr [rcx+44h], 20h
0x140010603  jz      loc_14001079E
0x140010609  cmp     byte ptr [rcx+41h], 2
0x14001060d  jb      loc_14001079E
0x140010613  mov     edx, 10h
0x140010618  jmp     loc_14001057E
0x14001061d  mov     ecx, [rsp+78h+arg_8]
0x140010624  lea     eax, [rcx-1]
0x140010627  lea     rbx, WPP_GLOBAL_Control
0x14001062e  lea     rdi, aUnexpected; "Unexpected"
0x140010635  lea     r12, aUntrusted; "Untrusted"
0x14001063c  test    eax, 0FFFFFFFDh
0x140010641  jz      loc_140010724
0x140010647  test    ecx, ecx
0x140010649  jz      short loc_140010665
0x14001064b  cmp     ecx, 2
0x14001064e  jz      short loc_14001065C
0x140010650  mov     r9, rdi
0x140010653  cmp     ecx, 4
0x140010656  cmovz   r9, r12
0x14001065a  jmp     short loc_14001066C
0x14001065c  lea     r9, aTrusted; "Trusted"
0x140010663  jmp     short loc_14001066C
0x140010665  lea     r9, aLocalmachine; "LocalMachine"
0x14001066c  mov     rax, cs:WPP_GLOBAL_Control
0x140010673  cmp     rax, rbx
0x140010676  jz      short loc_1400106A2
0x140010678  test    byte ptr [rax+44h], 20h
0x14001067c  jz      short loc_1400106A2
0x14001067e  cmp     byte ptr [rax+41h], 5
0x140010682  jb      short loc_1400106A2
0x140010684  mov     edx, 11h
0x140010689  mov     qword ptr [rsp+78h+var_50], rsi
0x14001068e  mov     dword ptr [rsp+78h+var_58], ecx
0x140010692  lea     r8, WPP_2f62e1cc15cd35a2451044e3f3cd4e75_Traceguids
0x140010699  mov     rcx, [rax+38h]
0x14001069d  call    WPP_SF_SdS
0x1400106a2  mov     rcx, [rbp+58h]
0x1400106a6  mov     rax, [rcx]
0x1400106a9  mov     [rsp+78h+var_40], 0
0x1400106b2  mov     dword ptr [rsp+78h+var_48], 0
0x1400106ba  mov     qword ptr [rsp+78h+var_50], 0
0x1400106c3  mov     [rsp+78h+var_58], 0
0x1400106cc  mov     r9d, 5001h
0x1400106d2  lea     r8, [rsp+78h+arg_8]
0x1400106da  mov     rdx, [rsp+78h+ppURI]
0x1400106e2  mov     rax, [rax+18h]
0x1400106e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400106eb  test    eax, eax
0x1400106ed  jns     short loc_14001071D
0x1400106ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400106f6  cmp     rcx, rbx
0x1400106f9  jz      loc_14001079E
0x1400106ff  test    byte ptr [rcx+44h], 20h
0x140010703  jz      loc_14001079E
0x140010709  cmp     byte ptr [rcx+41h], 2
0x14001070d  jb      loc_14001079E
0x140010713  mov     edx, 12h
0x140010718  jmp     loc_14001057E
0x14001071d  mov     ecx, [rsp+78h+arg_8]
0x140010724  mov     eax, ecx
0x140010726  test    ecx, ecx
0x140010728  jz      short loc_140010764
0x14001072a  sub     eax, 1
0x14001072d  jz      short loc_140010755
0x14001072f  sub     eax, 1
0x140010732  jz      short loc_14001074C
0x140010734  sub     eax, 1
0x140010737  jz      short loc_140010743
0x140010739  cmp     eax, 1
0x14001073c  jnz     short loc_14001076B
0x14001073e  mov     rdi, r12
0x140010741  jmp     short loc_14001076B
0x140010743  lea     rdi, aInternet; "Internet"
0x14001074a  jmp     short loc_14001076B
0x14001074c  lea     rdi, aTrusted; "Trusted"
0x140010753  jmp     short loc_14001076B
0x140010755  lea     rdi, aIntranet; "Intranet"
0x14001075c  mov     r14d, 1
0x140010762  jmp     short loc_14001076B
0x140010764  lea     rdi, aLocalmachine; "LocalMachine"
0x14001076b  mov     rdx, cs:WPP_GLOBAL_Control
0x140010772  cmp     rdx, rbx
0x140010775  jz      short loc_14001079E
0x140010777  test    byte ptr [rdx+44h], 20h
0x14001077b  jz      short loc_14001079E
0x14001077d  cmp     byte ptr [rdx+41h], 5
0x140010781  jb      short loc_14001079E
0x140010783  mov     [rsp+78h+var_48], rsi; __int64
0x140010788  mov     dword ptr [rsp+78h+var_50], ecx; char
0x14001078c  mov     [rsp+78h+var_58], rdi; __int64
0x140010791  mov     r9d, r14d
0x140010794  mov     rcx, [rdx+38h]; LoggerHandle
0x140010798  call    WPP_SF_dSdS
0x14001079d  nop
0x14001079e  lea     rcx, [rsp+78h+ppURI]
0x1400107a6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400107ab  mov     eax, r14d
0x1400107ae  mov     rbx, [rsp+78h+arg_0]
0x1400107b6  add     rsp, 50h
0x1400107ba  pop     r14
0x1400107bc  pop     r12
0x1400107be  pop     rdi
0x1400107bf  pop     rsi
0x1400107c0  pop     rbp
0x1400107c1  retn
```
