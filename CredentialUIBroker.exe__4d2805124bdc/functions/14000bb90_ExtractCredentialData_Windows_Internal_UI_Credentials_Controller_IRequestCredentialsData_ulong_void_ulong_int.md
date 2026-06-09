# ExtractCredentialData(Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData *,ulong *,void * *,ulong *,int *)

- ea: `0x14000bb90`
- end: `0x14000bd2e`
- name: `?ExtractCredentialData@@YAJPEAUIRequestCredentialsData@Controller@Credentials@UI@Internal@Windows@@PEAKPEAPEAX1PEAH@Z`
- size: `414`
- prototype: `__int64 __fastcall(struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData *, unsigned int *, void **, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400111ac`

## callees

- `0x140004de4`
- `0x14000bb90`
- `0x14000e920`
- `0x1400136fc`
- `0x14001f010`

## string_xrefs

- `0x14000bbf3`: `shellcommon\internal\shell\inc\creduxparameters.h`
- `0x14000bc4c`: `shellcommon\internal\shell\inc\creduxparameters.h`
- `0x14000bcde`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall ExtractCredentialData(
        struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData *a1,
        unsigned int *a2,
        void **a3,
        unsigned int *a4,
        int *a5)
{
  __int64 v8; // rax
  __int64 (__fastcall *v10)(struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v11; // eax
  unsigned int v12; // ebx
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rdi
  int v15; // eax
  __int64 v16; // rdx
  int *v17; // rbx
  __int64 v18; // rax
  int v19; // eax
  int v20; // edi
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+38h]
  char v24; // [rsp+60h] [rbp+40h] BYREF
  __int64 v25; // [rsp+68h] [rbp+48h] BYREF
  __int64 (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp+50h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v8 = *(_QWORD *)a1;
  v26 = 0;
  v10 = *(__int64 (__fastcall **)(struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(v8 + 48);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  v11 = v10(a1, &v26);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v26;
    v25 = 0;
    v14 = **v26;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    v15 = v14(v13, &GUID_e86e9b83_bc3e_4f34_8e22_8cda6723295c, &v25);
    v12 = v15;
    if ( v15 >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v25 + 24LL))(v25, a2);
      v12 = v15;
      if ( v15 >= 0 )
      {
        CredUXTelemetry::AuthPackId<unsigned long &>(a2);
        v15 = (*(__int64 (__fastcall **)(__int64, unsigned int *, void **))(*(_QWORD *)v25 + 48LL))(v25, a4, a3);
        v12 = v15;
        if ( v15 >= 0 )
        {
          v17 = a5;
          if ( a5 )
          {
            v18 = *(_QWORD *)a1;
            v24 = 0;
            v19 = (*(__int64 (__fastcall **)(struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData *, char *))(v18 + 56))(
                    a1,
                    &v24);
            v20 = v19;
            if ( v19 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x341,
                (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
                (const char *)(unsigned int)v19,
                savedregs);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
              v12 = v20;
              goto LABEL_15;
            }
            *v17 = v24 != 0;
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
          v12 = 0;
          goto LABEL_15;
        }
        v16 = 828;
      }
      else
      {
        v16 = 826;
      }
    }
    else
    {
      v16 = 824;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
      (const char *)(unsigned int)v15,
      savedregs);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x335,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
      (const char *)(unsigned int)v11,
      savedregs);
  }
LABEL_15:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  return v12;
}

```

## disassembly

```asm
0x14000bb90  push    rbp
0x14000bb92  push    rbx
0x14000bb93  push    rsi
0x14000bb94  push    rdi
0x14000bb95  push    r12
0x14000bb97  push    r14
0x14000bb99  push    r15; int
0x14000bb9b  mov     rbp, rsp
0x14000bb9e  sub     rsp, 20h
0x14000bba2  mov     dword ptr [rdx], 0
0x14000bba8  mov     rsi, rcx
0x14000bbab  mov     qword ptr [r8], 0
0x14000bbb2  mov     r15, r9
0x14000bbb5  mov     dword ptr [r9], 0
0x14000bbbc  mov     r12, r8
0x14000bbbf  mov     rax, [rcx]
0x14000bbc2  mov     r14, rdx
0x14000bbc5  lea     rcx, [rbp+arg_10]
0x14000bbc9  mov     [rbp+arg_10], 0
0x14000bbd1  mov     rbx, [rax+30h]
0x14000bbd5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000bbda  lea     rdx, [rbp+arg_10]
0x14000bbde  mov     rcx, rsi
0x14000bbe1  mov     rax, rbx
0x14000bbe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bbe9  mov     ebx, eax
0x14000bbeb  test    eax, eax
0x14000bbed  jns     short loc_14000BC0C
0x14000bbef  mov     rcx, [rbp+38h]; this
0x14000bbf3  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x14000bbfa  mov     r9d, eax; char *
0x14000bbfd  mov     edx, 335h; void *
0x14000bc02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bc07  jmp     loc_14000BD14
0x14000bc0c  mov     rbx, [rbp+arg_10]
0x14000bc10  lea     rcx, [rbp+arg_8]
0x14000bc14  mov     [rbp+arg_8], 0
0x14000bc1c  mov     rax, [rbx]
0x14000bc1f  mov     rdi, [rax]
0x14000bc22  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000bc27  lea     r8, [rbp+arg_8]
0x14000bc2b  mov     rcx, rbx
0x14000bc2e  lea     rdx, _GUID_e86e9b83_bc3e_4f34_8e22_8cda6723295c
0x14000bc35  mov     rax, rdi
0x14000bc38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bc3d  mov     ebx, eax
0x14000bc3f  test    eax, eax
0x14000bc41  jns     short loc_14000BC69
0x14000bc43  mov     edx, 338h; void *
0x14000bc48  mov     rcx, [rbp+38h]; this
0x14000bc4c  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x14000bc53  mov     r9d, eax; char *
0x14000bc56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bc5b  lea     rcx, [rbp+arg_8]
0x14000bc5f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000bc64  jmp     loc_14000BD14
0x14000bc69  mov     rcx, [rbp+arg_8]
0x14000bc6d  mov     rdx, r14
0x14000bc70  mov     rax, [rcx]
0x14000bc73  mov     rax, [rax+18h]
0x14000bc77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bc7c  mov     ebx, eax
0x14000bc7e  test    eax, eax
0x14000bc80  jns     short loc_14000BC89
0x14000bc82  mov     edx, 33Ah
0x14000bc87  jmp     short loc_14000BC48
0x14000bc89  mov     rcx, r14
0x14000bc8c  call    ??$AuthPackId@AEAK@CredUXTelemetry@@SAXAEAK@Z; CredUXTelemetry::AuthPackId<ulong &>(ulong &)
0x14000bc91  mov     rcx, [rbp+arg_8]
0x14000bc95  mov     r8, r12
0x14000bc98  mov     rdx, r15
0x14000bc9b  mov     rax, [rcx]
0x14000bc9e  mov     rax, [rax+30h]
0x14000bca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bca7  mov     ebx, eax
0x14000bca9  test    eax, eax
0x14000bcab  jns     short loc_14000BCB4
0x14000bcad  mov     edx, 33Ch
0x14000bcb2  jmp     short loc_14000BC48
0x14000bcb4  mov     rbx, [rbp+arg_20]
0x14000bcb8  test    rbx, rbx
0x14000bcbb  jz      short loc_14000BD09
0x14000bcbd  mov     rax, [rsi]
0x14000bcc0  lea     rdx, [rbp+arg_0]
0x14000bcc4  mov     rcx, rsi
0x14000bcc7  mov     [rbp+arg_0], 0
0x14000bccb  mov     rax, [rax+38h]
0x14000bccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bcd4  mov     edi, eax
0x14000bcd6  test    eax, eax
0x14000bcd8  jns     short loc_14000BCFF
0x14000bcda  mov     rcx, [rbp+38h]; this
0x14000bcde  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x14000bce5  mov     r9d, eax; char *
0x14000bce8  mov     edx, 341h; void *
0x14000bced  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bcf2  lea     rcx, [rbp+arg_8]
0x14000bcf6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000bcfb  mov     ebx, edi
0x14000bcfd  jmp     short loc_14000BD14
0x14000bcff  xor     eax, eax
0x14000bd01  cmp     [rbp+arg_0], al
0x14000bd04  setnz   al
0x14000bd07  mov     [rbx], eax
0x14000bd09  lea     rcx, [rbp+arg_8]
0x14000bd0d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000bd12  xor     ebx, ebx
0x14000bd14  lea     rcx, [rbp+arg_10]
0x14000bd18  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000bd1d  mov     eax, ebx
0x14000bd1f  add     rsp, 20h
0x14000bd23  pop     r15
0x14000bd25  pop     r14
0x14000bd27  pop     r12
0x14000bd29  pop     rdi
0x14000bd2a  pop     rsi
0x14000bd2b  pop     rbx
0x14000bd2c  pop     rbp
0x14000bd2d  retn
```
