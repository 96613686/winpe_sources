# CreateCredUXParams(ulong,_CREDUI_CONTEXT const *,CREDUI_INFO_INTERNAL *,ulong,ulong *,void const *,ulong,int *,ulong,Windows::Internal::UI::Credentials::Controller::CredUIStyle,Windows::Internal::UI::Credentials::Controller::ICredUXExtension *,Windows::Internal::UI::Credentials::Controller::IConsentUXContext *,Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt *,Windows::Internal::UI::Credentials::Controller::ICredUXParameters * *)

- ea: `0x14000af00`
- end: `0x14000b0d2`
- name: `?CreateCredUXParams@@YAJKPEBU_CREDUI_CONTEXT@@PEAUCREDUI_INFO_INTERNAL@@KPEAKPEBXKPEAHKW4CredUIStyle@Controller@Credentials@UI@Internal@Windows@@PEAUICredUXExtension@45678@PEAUIConsentUXContext@45678@PEAUICredUXSecurePrompt@45678@PEAPEAUICredUXParameters@45678@@Z`
- size: `466`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, __int64, __int64, int, int *, int, int, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400111ac`

## callees

- `0x140005d0c`
- `0x14000af00`
- `0x14000e920`
- `0x1400136fc`

## string_xrefs

- `0x14000afbe`: `shellcommon\internal\shell\inc\creduxparameters.h`
- `0x14000afd4`: `shellcommon\internal\shell\inc\creduxparameters.h`
- `0x14000b08b`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CreateCredUXParams(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        int a7,
        int *a8,
        int a9,
        int a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        _QWORD *a14)
{
  _QWORD *v14; // rdi
  int v15; // edx
  __int64 v16; // rdx
  int v18; // eax
  unsigned int v19; // ebx
  int v20; // [rsp+28h] [rbp-79h]
  int v21; // [rsp+28h] [rbp-79h]
  int v22; // [rsp+28h] [rbp-79h]
  int v23[2]; // [rsp+38h] [rbp-69h] BYREF
  __int64 v24; // [rsp+40h] [rbp-61h] BYREF
  __int64 v25; // [rsp+48h] [rbp-59h] BYREF
  _QWORD v26[3]; // [rsp+58h] [rbp-49h] BYREF
  int v27; // [rsp+70h] [rbp-31h]
  int v28; // [rsp+74h] [rbp-2Dh]
  __int64 v29; // [rsp+78h] [rbp-29h]
  __int64 v30; // [rsp+80h] [rbp-21h]
  int v31; // [rsp+88h] [rbp-19h]
  BOOL v32; // [rsp+8Ch] [rbp-15h]
  int v33; // [rsp+90h] [rbp-11h]
  int v34; // [rsp+94h] [rbp-Dh]
  int v35; // [rsp+98h] [rbp-9h]
  int v36; // [rsp+9Ch] [rbp-5h]
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+Fh]
  __int64 v38; // [rsp+C0h] [rbp+1Fh] BYREF

  v38 = a2;
  v14 = a14;
  v15 = a9;
  *(_QWORD *)v23 = 0;
  v24 = 0;
  *a14 = 0;
  v25 = 0;
  if ( (v15 & 0x27F3CC8C) != 0 )
  {
    v16 = 507;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
      (const char *)0x80070057LL,
      v20);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x315,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
      (const char *)0x80070057LL,
      v21);
    return 2147942487LL;
  }
  if ( (v15 & 0x120) == 0x120 )
  {
    v16 = 510;
    goto LABEL_14;
  }
  if ( (v15 & 0x110) != 0 && (v15 & 1) != 0 )
  {
    v16 = 513;
    goto LABEL_14;
  }
  if ( (v15 & 2) != 0 && !a8 )
  {
    v16 = 516;
    goto LABEL_14;
  }
  if ( (v15 & 0x20) != 0 && (!a6 || !a7) )
  {
    v16 = 519;
    goto LABEL_14;
  }
  v26[0] = 0;
  v28 = 0;
  v29 = a5;
  v26[1] = 0;
  v26[2] = a3;
  v27 = a4;
  v32 = (v15 & 2) != 0;
  v30 = a6;
  v31 = a7;
  if ( a8 )
    v33 = *a8;
  else
    v33 = 0;
  v35 = a10;
  v36 = 0;
  v38 = 0;
  a14 = v26;
  v34 = v15;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  v18 = Microsoft::WRL::Details::MakeAndInitialize<CredUXParameters,Windows::Internal::UI::Credentials::Controller::ICredUXParameters,CredUXParametersBlob *,Windows::Internal::UI::Credentials::Controller::ICredUXExtension * &,Windows::Internal::UI::Credentials::Controller::IConsentUXContext * &,Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt * &>(
          (unsigned int)&v38,
          (unsigned int)&a14,
          (unsigned int)&v25,
          (unsigned int)&v24,
          (__int64)v23);
  v19 = v18;
  if ( v18 >= 0 )
  {
    v19 = 0;
    *v14 = v38;
    v38 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x327,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
      (const char *)(unsigned int)v18,
      v22);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  return v19;
}

```

## disassembly

```asm
0x14000af00  mov     rax, rsp
0x14000af03  mov     [rax+8], rbx
0x14000af07  mov     [rax+18h], rdi
0x14000af0b  mov     [rax+10h], rdx
0x14000af0f  push    rbp
0x14000af10  lea     rbp, [rax-0Fh]
0x14000af14  sub     rsp, 0A0h
0x14000af1b  mov     rdi, [rbp+7+arg_68]
0x14000af1f  mov     r11d, r9d
0x14000af22  mov     edx, [rbp+7+arg_40]
0x14000af25  mov     rbx, r8
0x14000af28  mov     qword ptr [rbp+7+var_70], 0
0x14000af30  mov     [rbp+7+var_68], 0
0x14000af38  mov     qword ptr [rdi], 0
0x14000af3f  mov     [rbp+7+var_60], 0
0x14000af47  test    edx, 27F3CC8Ch
0x14000af4d  jz      short loc_14000AF56
0x14000af4f  mov     edx, 1FBh
0x14000af54  jmp     short loc_14000AFBA
0x14000af56  mov     ecx, 120h
0x14000af5b  mov     eax, edx
0x14000af5d  and     eax, ecx
0x14000af5f  cmp     eax, ecx
0x14000af61  jnz     short loc_14000AF6A
0x14000af63  mov     edx, 1FEh
0x14000af68  jmp     short loc_14000AFBA
0x14000af6a  test    edx, 110h
0x14000af70  setnz   cl
0x14000af73  test    dl, 1
0x14000af76  setnz   al
0x14000af79  test    al, cl
0x14000af7b  jz      short loc_14000AF84
0x14000af7d  mov     edx, 201h
0x14000af82  jmp     short loc_14000AFBA
0x14000af84  mov     rcx, [rbp+7+arg_38]
0x14000af88  mov     r8d, edx
0x14000af8b  and     r8d, 2
0x14000af8f  jz      short loc_14000AF9D
0x14000af91  test    rcx, rcx
0x14000af94  jnz     short loc_14000AF9D
0x14000af96  mov     edx, 204h
0x14000af9b  jmp     short loc_14000AFBA
0x14000af9d  mov     r9d, [rbp+7+arg_30]
0x14000afa1  mov     r10, [rbp+7+arg_28]
0x14000afa5  test    dl, 20h
0x14000afa8  jz      short loc_14000AFF5
0x14000afaa  test    r10, r10
0x14000afad  jz      short loc_14000AFB5
0x14000afaf  cmp     r9d, 1
0x14000afb3  jnb     short loc_14000AFF5
0x14000afb5  mov     edx, 207h; void *
0x14000afba  mov     rcx, [rbp+0Fh]; this
0x14000afbe  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x14000afc5  mov     r9d, 80070057h; char *
0x14000afcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000afd0  mov     rcx, [rbp+0Fh]; this
0x14000afd4  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x14000afdb  mov     r9d, 80070057h; char *
0x14000afe1  mov     edx, 315h; void *
0x14000afe6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000afeb  mov     eax, 80070057h
0x14000aff0  jmp     loc_14000B0BD
0x14000aff5  xor     eax, eax
0x14000aff7  mov     [rbp+7+var_50], 0
0x14000afff  mov     [rbp+7+var_34], eax
0x14000b002  mov     rax, [rbp+7+arg_20]
0x14000b006  mov     [rbp+7+var_30], rax
0x14000b00a  xor     eax, eax
0x14000b00c  test    r8d, r8d
0x14000b00f  mov     [rbp+7+var_48], 0
0x14000b017  mov     [rbp+7+var_40], rbx
0x14000b01b  setnz   al
0x14000b01e  mov     [rbp+7+var_38], r11d
0x14000b022  mov     [rbp+7+var_1C], eax
0x14000b025  mov     [rbp+7+var_28], r10
0x14000b029  mov     [rbp+7+var_20], r9d
0x14000b02d  test    rcx, rcx
0x14000b030  jz      short loc_14000B039
0x14000b032  mov     eax, [rcx]
0x14000b034  mov     [rbp+7+var_18], eax
0x14000b037  jmp     short loc_14000B040
0x14000b039  mov     [rbp+7+var_18], 0
0x14000b040  mov     eax, [rbp+7+arg_48]
0x14000b043  lea     rcx, [rbp+7+arg_8]
0x14000b047  mov     [rbp+7+var_10], eax
0x14000b04a  xor     eax, eax
0x14000b04c  mov     [rbp+7+var_C], eax
0x14000b04f  mov     [rbp+7+arg_8], rax
0x14000b053  lea     rax, [rbp+7+var_50]
0x14000b057  mov     [rbp+7+arg_68], rax
0x14000b05b  mov     [rbp+7+var_14], edx
0x14000b05e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000b063  lea     rax, [rbp+7+var_70]
0x14000b067  lea     r9, [rbp+7+var_68]
0x14000b06b  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x14000b070  lea     r8, [rbp+7+var_60]
0x14000b074  lea     rdx, [rbp+7+arg_68]
0x14000b078  lea     rcx, [rbp+7+arg_8]
0x14000b07c  call    ??$MakeAndInitialize@VCredUXParameters@@UICredUXParameters@Controller@Credentials@UI@Internal@Windows@@PEAUCredUXParametersBlob@@AEAPEAUICredUXExtension@34567@AEAPEAUIConsentUXContext@34567@AEAPEAUICredUXSecurePrompt@34567@@Details@WRL@Microsoft@@YAJPEAPEAUICredUXParameters@Controller@Credentials@UI@Internal@Windows@@$$QEAPEAUCredUXParametersBlob@@AEAPEAUICredUXExtension@45678@AEAPEAUIConsentUXContext@45678@AEAPEAUICredUXSecurePrompt@45678@@Z; Microsoft::WRL::Details::MakeAndInitialize<CredUXParameters,Windows::Internal::UI::Credentials::Controller::ICredUXParameters,CredUXParametersBlob *,Windows::Internal::UI::Credentials::Controller::ICredUXExtension * &,Windows::Internal::UI::Credentials::Controller::IConsentUXContext * &,Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt * &>(Windows::Internal::UI::Credentials::Controller::ICredUXParameters * *,CredUXParametersBlob * &&,Windows::Internal::UI::Credentials::Controller::ICredUXExtension * &,Windows::Internal::UI::Credentials::Controller::IConsentUXContext * &,Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt * &)
0x14000b081  mov     ebx, eax
0x14000b083  test    eax, eax
0x14000b085  jns     short loc_14000B0A1
0x14000b087  mov     rcx, [rbp+0Fh]; this
0x14000b08b  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x14000b092  mov     r9d, eax; char *
0x14000b095  mov     edx, 327h; void *
0x14000b09a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b09f  jmp     short loc_14000B0B2
0x14000b0a1  mov     rax, [rbp+7+arg_8]
0x14000b0a5  xor     ebx, ebx
0x14000b0a7  mov     [rdi], rax
0x14000b0aa  mov     [rbp+7+arg_8], 0
0x14000b0b2  lea     rcx, [rbp+7+arg_8]
0x14000b0b6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000b0bb  mov     eax, ebx
0x14000b0bd  lea     r11, [rsp+0A0h+var_s0]
0x14000b0c5  mov     rbx, [r11+10h]
0x14000b0c9  mov     rdi, [r11+20h]
0x14000b0cd  mov     rsp, r11
0x14000b0d0  pop     rbp
0x14000b0d1  retn
```
