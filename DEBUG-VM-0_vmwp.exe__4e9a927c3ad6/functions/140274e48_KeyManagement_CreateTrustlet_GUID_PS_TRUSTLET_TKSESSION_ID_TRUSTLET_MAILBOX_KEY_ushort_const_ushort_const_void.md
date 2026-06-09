# KeyManagement::CreateTrustlet(_GUID,_PS_TRUSTLET_TKSESSION_ID *,_TRUSTLET_MAILBOX_KEY *,ushort const *,ushort const *,void * *)

- ea: `0x140274e48`
- end: `0x1402751f9`
- name: `?CreateTrustlet@KeyManagement@@YAJU_GUID@@PEAU_PS_TRUSTLET_TKSESSION_ID@@PEAU_TRUSTLET_MAILBOX_KEY@@PEBG3PEAPEAX@Z`
- size: `945`
- prototype: `__int64 __fastcall(KeyManagement *__hidden this, struct _GUID *, struct _PS_TRUSTLET_TKSESSION_ID *, struct _TRUSTLET_MAILBOX_KEY *, const unsigned __int16 *, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x140274b90`

## callees

- `0x140132940`
- `0x1401335fc`
- `0x140274e48`

## import_xrefs

- `ntdll!NtClose` at `0x140275153`
- `ntdll!NtClose` at `0x140275163`
- `ntdll!NtClose` at `0x140275153`
- `ntdll!NtClose` at `0x140275163`
- `ntdll!RtlInitUnicodeString` at `0x140274efd`
- `ntdll!RtlInitUnicodeString` at `0x140274efd`
- `ntdll!RtlCreateProcessParametersEx` at `0x14027503e`
- `ntdll!RtlCreateProcessParametersEx` at `0x14027503e`
- `ntdll!RtlNtStatusToDosError` at `0x14027519c`
- `ntdll!RtlNtStatusToDosError` at `0x1402751ae`
- `ntdll!RtlNtStatusToDosError` at `0x1402751be`
- `ntdll!RtlNtStatusToDosError` at `0x14027519c`
- `ntdll!RtlNtStatusToDosError` at `0x1402751ae`
- `ntdll!RtlNtStatusToDosError` at `0x1402751be`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x140274f7c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x140274f7c`
- `ntdll!RtlFreeHeap` at `0x14027518a`
- `ntdll!RtlFreeHeap` at `0x14027518a`
- `ntdll!NtCreateUserProcess` at `0x14027512f`
- `ntdll!NtCreateUserProcess` at `0x14027512f`

## pseudocode

```c
__int64 __fastcall KeyManagement::CreateTrustlet(
        KeyManagement *this,
        struct _GUID *a2,
        struct _PS_TRUSTLET_TKSESSION_ID *a3,
        struct _TRUSTLET_MAILBOX_KEY *a4,
        const unsigned __int16 *a5,
        unsigned __int16 *a6)
{
  unsigned int v10; // edi
  NTSTATUS v11; // ebx
  __int128 v12; // xmm0
  struct _GUID v13; // xmm1
  __int128 v14; // xmm0
  __int64 v15; // rdx
  const unsigned __int16 *v16; // rax
  __int16 v17; // dx
  struct _RTL_USER_PROCESS_PARAMETERS *ProcessParameters; // r14
  __int64 v20; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  int v22; // [rsp+80h] [rbp-80h]
  _BYTE v23[4]; // [rsp+84h] [rbp-7Ch] BYREF
  HANDLE Handle; // [rsp+88h] [rbp-78h] BYREF
  HANDLE v25; // [rsp+90h] [rbp-70h] BYREF
  char v26; // [rsp+98h] [rbp-68h] BYREF
  __int128 v27; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v28[14]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v29; // [rsp+170h] [rbp+70h] BYREF
  int v30; // [rsp+178h] [rbp+78h] BYREF
  __int128 v31; // [rsp+180h] [rbp+80h]
  int v32; // [rsp+190h] [rbp+90h]
  __int128 v33; // [rsp+198h] [rbp+98h]
  int v34; // [rsp+1A8h] [rbp+A8h]
  __int128 v35; // [rsp+1B0h] [rbp+B0h]
  struct _GUID v36; // [rsp+1C0h] [rbp+C0h]
  _QWORD v37[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  char v38; // [rsp+1E0h] [rbp+E0h]

  memset_0(v28, 0, 0x68u);
  v29 = 0;
  memset_0(&v30, 0, 0x58u);
  memset_0(v37, 0, 0x58u);
  v20 = 0;
  v10 = 0;
  v27 = 0;
  DestinationString = 0;
  if ( a6 )
    *(_QWORD *)a6 = 0;
  memset_0(v23, 0, 0x64u);
  v22 = 104;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( !a2 )
  {
    v11 = -1073741811;
    goto LABEL_18;
  }
  v12 = *(_OWORD *)a3;
  v13 = a2[1];
  v30 = TrustletType_MailboxKey;
  v31 = v12;
  v32 = TrustletType_CollaborationId;
  v33 = *(_OWORD *)this;
  v29 = 2;
  v14 = (__int128)*a2;
  v34 = TrustletType_TkSessionId;
  v36 = v13;
  v35 = v14;
  v11 = RtlDosPathNameToNtPathName_U_WithStatus(a4, &DestinationString, 0, 0);
  if ( v11 >= 0 )
  {
    v27 = 0;
    if ( a5 )
    {
      v15 = 0x7FFF;
      v16 = a5;
      do
      {
        if ( !*v16 )
          break;
        ++v16;
        --v15;
      }
      while ( v15 );
      v11 = v15 == 0 ? 0xC000000D : 0;
      if ( !v15 )
        goto LABEL_18;
      v17 = 2 * v15;
      *((_QWORD *)&v27 + 1) = a5;
      LOWORD(v27) = -2 - v17;
      WORD1(v27) = -v17;
    }
    ProcessParameters = NtCurrentPeb()->ProcessParameters;
    v11 = RtlCreateProcessParametersEx(&v20, &DestinationString, 0, 0, &v27, 0, 0, 0, 0, 0, 1);
    if ( v11 >= 0 )
    {
      *(_DWORD *)(v20 + 1032) = ProcessParameters[1].Flags;
      memset_0(v37, 0, 0x58u);
      v37[0] = 88;
      v28[3] = &v26;
      v28[6] = DestinationString.Length;
      v28[7] = DestinationString.Buffer;
      v28[11] = &v29;
      v38 = 4;
      v28[1] = 65539;
      v28[2] = 16;
      v28[4] = 0;
      v28[5] = 131077;
      v28[8] = 0;
      v28[9] = 131090;
      v28[10] = 96;
      v28[12] = 0;
      v28[0] = 104;
      v11 = NtCreateUserProcess(&Handle, &v25, 0x2000000, 0x2000000, 0, 0, 256, 0, v20, v37, v28);
      if ( v11 >= 0 )
      {
        if ( a6 )
          *(_QWORD *)a6 = Handle;
        else
          NtClose(Handle);
        NtClose(v25);
      }
    }
  }
LABEL_18:
  if ( DestinationString.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
  if ( v11 < 0 )
  {
    if ( (int)RtlNtStatusToDosError(v11) > 0 )
      return (unsigned __int16)RtlNtStatusToDosError(v11) | 0x80070000;
    else
      return RtlNtStatusToDosError(v11);
  }
  return v10;
}

```

## disassembly

```asm
0x140274e48  push    rbp
0x140274e4a  push    rbx
0x140274e4b  push    rsi
0x140274e4c  push    rdi
0x140274e4d  push    r12
0x140274e4f  push    r13
0x140274e51  push    r14
0x140274e53  push    r15
0x140274e55  lea     rbp, [rsp-148h]
0x140274e5d  sub     rsp, 248h
0x140274e64  mov     rax, cs:__security_cookie
0x140274e6b  xor     rax, rsp
0x140274e6e  mov     [rbp+180h+var_50], rax
0x140274e75  mov     rsi, [rbp+180h+arg_28]
0x140274e7c  mov     rbx, rdx
0x140274e7f  xor     edx, edx; Val
0x140274e81  mov     r14, r8
0x140274e84  mov     r15, rcx
0x140274e87  mov     r12, r9
0x140274e8a  lea     rcx, [rbp+180h+var_180]; void *
0x140274e8e  lea     r8d, [rdx+68h]; Size
0x140274e92  call    memset_0
0x140274e97  xor     r13d, r13d
0x140274e9a  lea     rcx, [rbp+180h+var_108]; void *
0x140274e9e  xor     edx, edx; Val
0x140274ea0  mov     [rbp+180h+var_110], r13
0x140274ea4  lea     edi, [r13+58h]
0x140274ea8  mov     r8d, edi; Size
0x140274eab  call    memset_0
0x140274eb0  mov     r8d, edi; Size
0x140274eb3  lea     rcx, [rbp+180h+var_B0]; void *
0x140274eba  xor     edx, edx; Val
0x140274ebc  call    memset_0
0x140274ec1  mov     [rsp+280h+var_220], r13
0x140274ec6  xorps   xmm0, xmm0
0x140274ec9  xorps   xmm1, xmm1
0x140274ecc  mov     edi, r13d
0x140274ecf  movups  [rbp+180h+var_190], xmm0
0x140274ed3  movups  xmmword ptr [rsp+280h+DestinationString.Length], xmm1
0x140274ed8  test    rsi, rsi
0x140274edb  jz      short loc_140274EE0
0x140274edd  mov     [rsi], r13
0x140274ee0  xor     edx, edx; Val
0x140274ee2  lea     rcx, [rbp+180h+var_1FC]; void *
0x140274ee6  lea     r8d, [rdx+64h]; Size
0x140274eea  call    memset_0
0x140274eef  xor     edx, edx; SourceString
0x140274ef1  mov     [rbp+180h+var_200], 68h ; 'h'
0x140274ef8  lea     rcx, [rsp+280h+DestinationString]; DestinationString
0x140274efd  call    cs:__imp_RtlInitUnicodeString
0x140274f04  nop     dword ptr [rax+rax+00h]
0x140274f09  test    rbx, rbx
0x140274f0c  jnz     short loc_140274F18
0x140274f0e  mov     ebx, 0C000000Dh
0x140274f13  jmp     loc_14027516F
0x140274f18  movups  xmm0, xmmword ptr [r14]
0x140274f1c  mov     eax, cs:TrustletType_MailboxKey
0x140274f22  lea     rdx, [rsp+280h+DestinationString]
0x140274f27  movups  xmm1, xmmword ptr [rbx+10h]
0x140274f2b  mov     [rbp+180h+var_108], eax
0x140274f2e  xor     r9d, r9d
0x140274f31  mov     eax, cs:TrustletType_CollaborationId
0x140274f37  xor     r8d, r8d
0x140274f3a  movdqu  [rbp+180h+var_100], xmm0
0x140274f42  mov     rcx, r12
0x140274f45  mov     [rbp+180h+var_F0], eax
0x140274f4b  movaps  xmm0, xmmword ptr [r15]
0x140274f4f  mov     eax, cs:TrustletType_TkSessionId
0x140274f55  movdqu  [rbp+180h+var_E8], xmm0
0x140274f5d  mov     [rbp+180h+var_110], 2
0x140274f65  movups  xmm0, xmmword ptr [rbx]
0x140274f68  mov     [rbp+180h+var_D8], eax
0x140274f6e  movaps  [rbp+180h+var_C0], xmm1
0x140274f75  movaps  [rbp+180h+var_D0], xmm0
0x140274f7c  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x140274f83  nop     dword ptr [rax+rax+00h]
0x140274f88  mov     ebx, eax
0x140274f8a  test    eax, eax
0x140274f8c  js      loc_14027516F
0x140274f92  mov     r8, [rbp+180h+arg_20]
0x140274f99  xorps   xmm0, xmm0
0x140274f9c  movups  [rbp+180h+var_190], xmm0
0x140274fa0  test    r8, r8
0x140274fa3  jz      short loc_140274FF7
0x140274fa5  mov     edx, 7FFFh
0x140274faa  mov     rax, r8
0x140274fad  mov     r9d, 2
0x140274fb3  cmp     [rax], r13w
0x140274fb7  jz      short loc_140274FC2
0x140274fb9  add     rax, r9
0x140274fbc  sub     rdx, 1
0x140274fc0  jnz     short loc_140274FB3
0x140274fc2  mov     rax, rdx
0x140274fc5  mov     ebx, 0C000000Dh
0x140274fca  neg     rax
0x140274fcd  sbb     ecx, ecx
0x140274fcf  not     ecx
0x140274fd1  and     ebx, ecx
0x140274fd3  test    rdx, rdx
0x140274fd6  jz      loc_14027516F
0x140274fdc  add     dx, dx
0x140274fdf  mov     qword ptr [rbp+180h+var_190+8], r8
0x140274fe3  mov     eax, 0FFFEh
0x140274fe8  sub     ax, dx
0x140274feb  mov     word ptr [rbp+180h+var_190], ax
0x140274fef  add     ax, r9w
0x140274ff3  mov     word ptr [rbp+180h+var_190+2], ax
0x140274ff7  mov     rax, gs:60h
0x140275000  lea     rdx, [rsp+280h+DestinationString]
0x140275005  mov     dword ptr [rsp+280h+var_230], 1
0x14027500d  lea     rcx, [rsp+280h+var_220]
0x140275012  mov     [rsp+280h+var_238], r13
0x140275017  xor     r9d, r9d
0x14027501a  mov     [rsp+280h+var_240], r13
0x14027501f  xor     r8d, r8d
0x140275022  mov     r14, [rax+20h]
0x140275026  lea     rax, [rbp+180h+var_190]
0x14027502a  mov     [rsp+280h+var_248], r13
0x14027502f  mov     [rsp+280h+var_250], r13
0x140275034  mov     [rsp+280h+var_258], r13
0x140275039  mov     [rsp+280h+var_260], rax
0x14027503e  call    cs:__imp_RtlCreateProcessParametersEx
0x140275045  nop     dword ptr [rax+rax+00h]
0x14027504a  mov     ebx, eax
0x14027504c  test    eax, eax
0x14027504e  js      loc_14027516F
0x140275054  mov     ecx, [r14+408h]
0x14027505b  mov     ebx, 58h ; 'X'
0x140275060  mov     rax, [rsp+280h+var_220]
0x140275065  mov     r8d, ebx; Size
0x140275068  xor     edx, edx; Val
0x14027506a  mov     [rax+408h], ecx
0x140275070  lea     rcx, [rbp+180h+var_B0]; void *
0x140275077  call    memset_0
0x14027507c  lea     rax, [rbp+180h+var_1E8]
0x140275080  mov     [rbp+180h+var_B0], rbx
0x140275087  mov     [rbp+180h+var_168], rax
0x14027508b  lea     rdx, [rbp+180h+var_1F0]
0x14027508f  movzx   eax, [rsp+280h+DestinationString.Length]
0x140275094  lea     rcx, [rbp+180h+Handle]
0x140275098  mov     [rbp+180h+var_150], rax
0x14027509c  mov     r8d, 2000000h
0x1402750a2  mov     rax, [rsp+280h+DestinationString.Buffer]
0x1402750a7  mov     r9d, r8d
0x1402750aa  mov     [rbp+180h+var_148], rax
0x1402750ae  lea     rax, [rbp+180h+var_110]
0x1402750b2  mov     [rbp+180h+var_128], rax
0x1402750b6  lea     rax, [rbp+180h+var_180]
0x1402750ba  mov     [rsp+280h+var_230], rax
0x1402750bf  lea     rax, [rbp+180h+var_B0]
0x1402750c6  mov     [rsp+280h+var_238], rax
0x1402750cb  mov     rax, [rsp+280h+var_220]
0x1402750d0  mov     [rsp+280h+var_240], rax
0x1402750d5  mov     dword ptr [rsp+280h+var_248], r13d
0x1402750da  mov     dword ptr [rsp+280h+var_250], 100h
0x1402750e2  mov     [rsp+280h+var_258], r13
0x1402750e7  mov     [rsp+280h+var_260], r13
0x1402750ec  mov     [rbp+180h+var_A0], 4
0x1402750f3  mov     [rbp+180h+var_178], 10003h
0x1402750fb  mov     [rbp+180h+var_170], 10h
0x140275103  mov     [rbp+180h+var_160], r13
0x140275107  mov     [rbp+180h+var_158], 20005h
0x14027510f  mov     [rbp+180h+var_140], r13
0x140275113  mov     [rbp+180h+var_138], 20012h
0x14027511b  mov     [rbp+180h+var_130], 60h ; '`'
0x140275123  mov     [rbp+180h+var_120], r13
0x140275127  mov     [rbp+180h+var_180], 68h ; 'h'
0x14027512f  call    cs:__imp_NtCreateUserProcess
0x140275136  nop     dword ptr [rax+rax+00h]
0x14027513b  mov     ebx, eax
0x14027513d  test    eax, eax
0x14027513f  js      short loc_14027516F
0x140275141  test    rsi, rsi
0x140275144  jz      short loc_14027514F
0x140275146  mov     rax, [rbp+180h+Handle]
0x14027514a  mov     [rsi], rax
0x14027514d  jmp     short loc_14027515F
0x14027514f  mov     rcx, [rbp+180h+Handle]; Handle
0x140275153  call    cs:__imp_NtClose
0x14027515a  nop     dword ptr [rax+rax+00h]
0x14027515f  mov     rcx, [rbp+180h+var_1F0]; Handle
0x140275163  call    cs:__imp_NtClose
0x14027516a  nop     dword ptr [rax+rax+00h]
0x14027516f  cmp     [rsp+280h+DestinationString.Buffer], r13
0x140275174  jz      short loc_140275196
0x140275176  mov     rcx, gs:60h
0x14027517f  xor     edx, edx; Flags
0x140275181  mov     r8, [rsp+280h+DestinationString.Buffer]; P
0x140275186  mov     rcx, [rcx+30h]; HeapHandle
0x14027518a  call    cs:__imp_RtlFreeHeap
0x140275191  nop     dword ptr [rax+rax+00h]
0x140275196  test    ebx, ebx
0x140275198  jns     short loc_1402751D3
0x14027519a  mov     ecx, ebx; Status
0x14027519c  call    cs:__imp_RtlNtStatusToDosError
0x1402751a3  nop     dword ptr [rax+rax+00h]
0x1402751a8  mov     ecx, ebx; Status
0x1402751aa  test    eax, eax
0x1402751ac  jg      short loc_1402751BE
0x1402751ae  call    cs:__imp_RtlNtStatusToDosError
0x1402751b5  nop     dword ptr [rax+rax+00h]
0x1402751ba  mov     edi, eax
0x1402751bc  jmp     short loc_1402751D3
0x1402751be  call    cs:__imp_RtlNtStatusToDosError
0x1402751c5  nop     dword ptr [rax+rax+00h]
0x1402751ca  movzx   edi, ax
0x1402751cd  or      edi, 80070000h
0x1402751d3  mov     eax, edi
0x1402751d5  mov     rcx, [rbp+180h+var_50]
0x1402751dc  xor     rcx, rsp; StackCookie
0x1402751df  call    __security_check_cookie
0x1402751e4  add     rsp, 248h
0x1402751eb  pop     r15
0x1402751ed  pop     r14
0x1402751ef  pop     r13
0x1402751f1  pop     r12
0x1402751f3  pop     rdi
0x1402751f4  pop     rsi
0x1402751f5  pop     rbx
0x1402751f6  pop     rbp
0x1402751f7  retn
```
