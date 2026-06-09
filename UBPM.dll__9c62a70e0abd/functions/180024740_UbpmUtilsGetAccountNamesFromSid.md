# UbpmUtilsGetAccountNamesFromSid

- ea: `0x180024740`
- end: `0x180024be3`
- name: `UbpmUtilsGetAccountNamesFromSid`
- size: `1187`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800057e0`
- `0x1800060d0`
- `0x180007000`
- `0x18000a230`
- `0x18000aff0`
- `0x180011a90`
- `0x180023b50`
- `0x180024630`

## callees

- `0x18000fbf0`
- `0x1800150c0`
- `0x180024740`
- `0x180032f78`
- `0x1800351ec`
- `0x180040222`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18002488d`
- `ntdll!RtlAllocateHeap` at `0x18002488d`
- `ntdll!RtlNtStatusToDosError` at `0x18002499f`
- `ntdll!RtlNtStatusToDosError` at `0x1800249d7`
- `ntdll!RtlNtStatusToDosError` at `0x18002499f`
- `ntdll!RtlNtStatusToDosError` at `0x1800249d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024b8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024b8f`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupTranslateSids` at `0x1800247dd`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupTranslateSids` at `0x1800247dd`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800247af`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800247af`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x180024958`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x180024958`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18002492b`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180024943`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18002492b`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180024943`

## pseudocode

```c
__int64 __fastcall UbpmUtilsGetAccountNamesFromSid(void *a1, int a2, _QWORD *a3, _QWORD *a4, _QWORD *a5)
{
  _WORD *v7; // rsi
  _WORD *v8; // r14
  _WORD *v9; // rbx
  int v11; // eax
  int v12; // eax
  unsigned __int64 v13; // rdx
  __int64 Use; // r9
  _QWORD *v15; // r15
  PLSA_TRUST_INFORMATION v16; // rcx
  unsigned __int64 v17; // rdi
  SIZE_T v18; // r8
  _WORD *Heap; // rax
  unsigned __int64 v20; // rdi
  ULONG v21; // edi
  PLSA_TRANSLATED_NAME v22; // r8
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  unsigned __int64 Length; // rdi
  PWSTR Buffer; // r15
  _WORD *v28; // rax
  PLSA_TRUST_INFORMATION Domains; // rcx
  size_t v30; // rdi
  PWSTR v31; // r15
  _WORD *v32; // rax
  int v33; // [rsp+38h] [rbp-31h]
  PLSA_TRANSLATED_NAME Names; // [rsp+40h] [rbp-29h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+48h] [rbp-21h] BYREF
  PVOID PolicyHandle; // [rsp+50h] [rbp-19h] BYREF
  void *Src; // [rsp+58h] [rbp-11h]
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  PSID Sids; // [rsp+C8h] [rbp+5Fh] BYREF

  Sids = a1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ReferencedDomains = 0;
  Names = 0;
  v7 = 0;
  PolicyHandle = 0;
  v8 = 0;
  v9 = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  v11 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 0x800u, &PolicyHandle);
  if ( v11 < 0 )
  {
    v21 = RtlNtStatusToDosError(v11);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v25 = 22;
LABEL_41:
    WPP_SF_d(v24[2], v25, WPP_134408c016563692a0776b6ad2359b4f_Traceguids, v21);
    goto LABEL_19;
  }
  v12 = LsaLookupTranslateSids(PolicyHandle, 1u, &Sids, &ReferencedDomains, &Names);
  if ( v12 < 0 )
  {
    v21 = RtlNtStatusToDosError(v12);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v25 = 23;
    goto LABEL_41;
  }
  if ( !ReferencedDomains || !Names )
  {
    v21 = 13;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v25 = 24;
    goto LABEL_41;
  }
  Use = (unsigned int)Names->Use;
  if ( (_DWORD)Use != a2 )
  {
    v21 = 13;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_134408c016563692a0776b6ad2359b4f_Traceguids, Use);
    goto LABEL_19;
  }
  if ( Names->DomainIndex < 0 )
  {
    v21 = 13;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v25 = 26;
    goto LABEL_41;
  }
  if ( !ReferencedDomains->Entries )
  {
    v21 = 13;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v25 = 27;
    goto LABEL_41;
  }
  if ( a4 )
  {
    Length = Names->Name.Length;
    Buffer = Names->Name.Buffer;
    v28 = UbpmAlloc((unsigned int)(Length + 2));
    v8 = v28;
    if ( !v28 )
    {
      v21 = 14;
      goto LABEL_19;
    }
    memcpy_0(v28, Buffer, (unsigned int)Length);
    v8[Length >> 1] = 0;
  }
  if ( a3 )
  {
    Domains = ReferencedDomains->Domains;
    v30 = Domains[Names->DomainIndex].Name.Length;
    v31 = Domains[Names->DomainIndex].Name.Buffer;
    v32 = UbpmAlloc((unsigned int)(v30 + 2));
    v7 = v32;
    if ( !v32 )
    {
      v21 = 14;
      goto LABEL_19;
    }
    memcpy_0(v32, v31, v30);
    v7[v30 >> 1] = 0;
  }
  v15 = a5;
  if ( a5 )
  {
    v16 = ReferencedDomains->Domains;
    v17 = v16[Names->DomainIndex].Name.Length;
    v18 = (unsigned int)v17 + Names->Name.Length + 4;
    v33 = v16[Names->DomainIndex].Name.Length;
    Src = v16[Names->DomainIndex].Name.Buffer;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v18);
    v9 = Heap;
    if ( !Heap )
    {
      SetLastError(8u);
      v21 = 14;
      goto LABEL_19;
    }
    memcpy_0(Heap, Src, (unsigned int)v17);
    v20 = v17 >> 1;
    v9[v20] = 92;
    memcpy_0(&v9[v20 + 1], Names->Name.Buffer, Names->Name.Length);
    v13 = (unsigned __int64)(v33 + (unsigned int)Names->Name.Length) >> 1;
    v9[v13 + 1] = 0;
  }
  v21 = 0;
  if ( a4 )
  {
    *a4 = v8;
    v8 = 0;
  }
  if ( a3 )
  {
    *a3 = v7;
    v7 = 0;
  }
  if ( v15 )
  {
    *v15 = v9;
    v9 = 0;
  }
LABEL_19:
  if ( ReferencedDomains )
    LsaLookupFreeMemory(ReferencedDomains);
  v22 = Names;
  if ( Names )
    LsaLookupFreeMemory(Names);
  if ( PolicyHandle )
    LsaLookupClose(PolicyHandle);
  if ( v8 )
    UBPM_MIDL_user_free(v8, v13, v22, Use);
  if ( v7 )
    UBPM_MIDL_user_free(v7, v13, v22, Use);
  if ( v9 )
    UBPM_MIDL_user_free(v9, v13, v22, Use);
  return v21;
}

```

## disassembly

```asm
0x180024740  mov     rax, rsp
0x180024743  mov     [rax+8], rcx
0x180024747  push    rbp
0x180024748  push    rbx
0x180024749  push    rdi
0x18002474a  lea     rbp, [rax-57h]
0x18002474e  sub     rsp, 0A0h
0x180024755  mov     [rax+10h], rsi
0x180024759  lea     rcx, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18002475d  mov     [rax+18h], r12
0x180024761  mov     edi, edx
0x180024763  mov     [rax+20h], r13
0x180024767  xorps   xmm0, xmm0
0x18002476a  mov     [rax-20h], r14
0x18002476e  mov     r13, r8
0x180024771  mov     [rax-28h], r15
0x180024775  lea     r8, [rbp+4Fh+PolicyHandle]; PolicyHandle
0x180024779  xor     eax, eax
0x18002477b  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x180024783  mov     edx, 800h; AccessMask
0x180024788  mov     [rbp+4Fh+ReferencedDomains], rax
0x18002478c  mov     [rbp+4Fh+Names], rax
0x180024790  mov     esi, eax
0x180024792  mov     [rbp+4Fh+PolicyHandle], rax
0x180024796  mov     r14d, eax
0x180024799  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], rax
0x18002479d  mov     ebx, eax
0x18002479f  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x1800247a3  mov     r12, r9
0x1800247a6  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1800247aa  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800247af  call    cs:__imp_LsaLookupOpenLocalPolicy
0x1800247b6  nop     dword ptr [rax+rax+00h]
0x1800247bb  test    eax, eax
0x1800247bd  js      loc_18002499D
0x1800247c3  mov     rcx, [rbp+4Fh+PolicyHandle]; PolicyHandle
0x1800247c7  lea     rax, [rbp+4Fh+Names]
0x1800247cb  lea     r9, [rbp+4Fh+ReferencedDomains]; ReferencedDomains
0x1800247cf  mov     [rsp+20h], rax; Names
0x1800247d4  lea     r8, [rbp+4Fh+Sids]; Sids
0x1800247d8  mov     edx, 1; Count
0x1800247dd  call    cs:__imp_LsaLookupTranslateSids
0x1800247e4  nop     dword ptr [rax+rax+00h]
0x1800247e9  test    eax, eax
0x1800247eb  js      loc_1800249D5
0x1800247f1  cmp     [rbp+4Fh+ReferencedDomains], rbx
0x1800247f5  jz      loc_180024A0D
0x1800247fb  mov     r8, [rbp+4Fh+Names]
0x1800247ff  test    r8, r8
0x180024802  jz      loc_180024A0D
0x180024808  mov     r9d, [r8]
0x18002480b  cmp     r9d, edi
0x18002480e  jnz     loc_180024A50
0x180024814  mov     rax, r8
0x180024817  cmp     [rax+18h], ebx
0x18002481a  jl      loc_180024ACD
0x180024820  mov     rax, [rbp+4Fh+ReferencedDomains]
0x180024824  cmp     [rax], ebx
0x180024826  jz      loc_180024AFD
0x18002482c  test    r12, r12
0x18002482f  jnz     loc_180024A94
0x180024835  test    r13, r13
0x180024838  jnz     loc_180024B37
0x18002483e  mov     r15, [rbp+4Fh+arg_20]
0x180024842  test    r15, r15
0x180024845  jz      loc_1800248EC
0x18002484b  mov     r8, [rbp+4Fh+Names]
0x18002484f  movsxd  rax, dword ptr [r8+18h]
0x180024853  movzx   r8d, word ptr [r8+8]
0x180024858  add     r8d, 4
0x18002485c  lea     rdx, [rax+rax*2]
0x180024860  mov     rax, [rbp+4Fh+ReferencedDomains]
0x180024864  mov     rcx, [rax+8]
0x180024868  movzx   edi, word ptr [rcx+rdx*8]
0x18002486c  mov     rax, [rcx+rdx*8+8]
0x180024871  add     r8d, edi; Size
0x180024874  mov     rcx, gs:60h
0x18002487d  mov     edx, 8; Flags
0x180024882  mov     [rbp+4Fh+var_80], edi
0x180024885  mov     [rbp+4Fh+Src], rax
0x180024889  mov     rcx, [rcx+30h]; HeapHandle
0x18002488d  call    cs:__imp_RtlAllocateHeap
0x180024894  nop     dword ptr [rax+rax+00h]
0x180024899  mov     rbx, rax
0x18002489c  test    rax, rax
0x18002489f  jz      loc_180024B8A
0x1800248a5  mov     rdx, [rbp+4Fh+Src]; Src
0x1800248a9  mov     r8d, edi; Size
0x1800248ac  mov     rcx, rax; void *
0x1800248af  call    memcpy_0
0x1800248b4  shr     rdi, 1
0x1800248b7  mov     word ptr [rbx+rdi*2], 5Ch ; '\'
0x1800248bd  lea     rcx, [rdi+1]
0x1800248c1  mov     rdx, [rbp+4Fh+Names]
0x1800248c5  lea     rcx, [rbx+rcx*2]; void *
0x1800248c9  movzx   r8d, word ptr [rdx+8]; Size
0x1800248ce  mov     rdx, [rdx+10h]; Src
0x1800248d2  call    memcpy_0
0x1800248d7  mov     rax, [rbp+4Fh+Names]
0x1800248db  movzx   edx, word ptr [rax+8]
0x1800248df  add     edx, [rbp+4Fh+var_80]
0x1800248e2  shr     rdx, 1
0x1800248e5  xor     eax, eax
0x1800248e7  mov     [rbx+rdx*2+2], ax
0x1800248ec  xor     edi, edi
0x1800248ee  test    r12, r12
0x1800248f1  jnz     loc_180024BA5
0x1800248f7  test    r13, r13
0x1800248fa  jnz     loc_180024BB1
0x180024900  test    r15, r15
0x180024903  jz      short loc_18002490A
0x180024905  mov     [r15], rbx
0x180024908  xor     ebx, ebx
0x18002490a  mov     rcx, [rbp+4Fh+ReferencedDomains]; Buffer
0x18002490e  mov     r15, [rsp+0B0h+var_20]
0x180024916  mov     r13, [rsp+0B0h+arg_18]
0x18002491e  mov     r12, [rsp+0B0h+arg_10]
0x180024926  test    rcx, rcx
0x180024929  jz      short loc_180024937
0x18002492b  call    cs:__imp_LsaLookupFreeMemory
0x180024932  nop     dword ptr [rax+rax+00h]
0x180024937  mov     r8, [rbp+4Fh+Names]
0x18002493b  test    r8, r8
0x18002493e  jz      short loc_18002494F
0x180024940  mov     rcx, r8; Buffer
0x180024943  call    cs:__imp_LsaLookupFreeMemory
0x18002494a  nop     dword ptr [rax+rax+00h]
0x18002494f  mov     rcx, [rbp+4Fh+PolicyHandle]; ObjectHandle
0x180024953  test    rcx, rcx
0x180024956  jz      short loc_180024964
0x180024958  call    cs:__imp_LsaLookupClose
0x18002495f  nop     dword ptr [rax+rax+00h]
0x180024964  test    r14, r14
0x180024967  jnz     loc_180024BBC
0x18002496d  mov     r14, [rsp+98h]
0x180024975  test    rsi, rsi
0x180024978  jnz     loc_180024BC9
0x18002497e  mov     rsi, [rsp+0B0h+arg_8]
0x180024986  test    rbx, rbx
0x180024989  jnz     loc_180024BD6
0x18002498f  mov     eax, edi
0x180024991  add     rsp, 0A0h
0x180024998  pop     rdi
0x180024999  pop     rbx
0x18002499a  pop     rbp
0x18002499b  retn
0x18002499d  mov     ecx, eax; Status
0x18002499f  call    cs:__imp_RtlNtStatusToDosError
0x1800249a6  nop     dword ptr [rax+rax+00h]
0x1800249ab  mov     edi, eax
0x1800249ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249b4  lea     rax, WPP_GLOBAL_Control
0x1800249bb  cmp     rcx, rax
0x1800249be  jz      loc_18002490A
0x1800249c4  test    byte ptr [rcx+1Ch], 1
0x1800249c8  jz      loc_18002490A
0x1800249ce  mov     edx, 16h
0x1800249d3  jmp     short loc_180024A38
0x1800249d5  mov     ecx, eax; Status
0x1800249d7  call    cs:__imp_RtlNtStatusToDosError
0x1800249de  nop     dword ptr [rax+rax+00h]
0x1800249e3  mov     edi, eax
0x1800249e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249ec  lea     rax, WPP_GLOBAL_Control
0x1800249f3  cmp     rcx, rax
0x1800249f6  jz      loc_18002490A
0x1800249fc  test    byte ptr [rcx+1Ch], 1
0x180024a00  jz      loc_18002490A
0x180024a06  mov     edx, 17h
0x180024a0b  jmp     short loc_180024A38
0x180024a0d  mov     edi, 0Dh
0x180024a12  mov     rcx, cs:WPP_GLOBAL_Control
0x180024a19  lea     rax, WPP_GLOBAL_Control
0x180024a20  cmp     rcx, rax
0x180024a23  jz      loc_18002490A
0x180024a29  test    byte ptr [rcx+1Ch], 1
0x180024a2d  jz      loc_18002490A
0x180024a33  mov     edx, 18h
0x180024a38  mov     rcx, [rcx+10h]
0x180024a3c  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180024a43  mov     r9d, edi
0x180024a46  call    WPP_SF_d
0x180024a4b  jmp     loc_18002490A
0x180024a50  mov     edi, 0Dh
0x180024a55  mov     rcx, cs:WPP_GLOBAL_Control
0x180024a5c  lea     rax, WPP_GLOBAL_Control
0x180024a63  cmp     rcx, rax
0x180024a66  jz      loc_18002490A
0x180024a6c  test    byte ptr [rcx+1Ch], 1
0x180024a70  jz      loc_18002490A
0x180024a76  mov     rcx, [rcx+10h]
0x180024a7a  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180024a81  mov     edx, 19h
0x180024a86  mov     [rsp+20h], edi
0x180024a8a  call    WPP_SF_dd
0x180024a8f  jmp     loc_18002490A
0x180024a94  mov     rax, [rbp+4Fh+Names]
0x180024a98  movzx   edi, word ptr [rax+8]
0x180024a9c  mov     r15, [rax+10h]
0x180024aa0  lea     ecx, [rdi+2]; Size
0x180024aa3  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180024aa8  mov     r14, rax
0x180024aab  test    rax, rax
0x180024aae  jz      short loc_180024B2D
0x180024ab0  mov     r8d, edi; Size
0x180024ab3  mov     rdx, r15; Src
0x180024ab6  mov     rcx, rax; void *
0x180024ab9  call    memcpy_0
0x180024abe  shr     rdi, 1
0x180024ac1  xor     eax, eax
0x180024ac3  mov     [r14+rdi*2], ax
0x180024ac8  jmp     loc_180024835
0x180024acd  mov     edi, 0Dh
0x180024ad2  mov     rcx, cs:WPP_GLOBAL_Control
0x180024ad9  lea     rax, WPP_GLOBAL_Control
0x180024ae0  cmp     rcx, rax
0x180024ae3  jz      loc_18002490A
0x180024ae9  test    byte ptr [rcx+1Ch], 1
0x180024aed  jz      loc_18002490A
0x180024af3  mov     edx, 1Ah
0x180024af8  jmp     loc_180024A38
0x180024afd  mov     edi, 0Dh
0x180024b02  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b09  lea     rax, WPP_GLOBAL_Control
0x180024b10  cmp     rcx, rax
0x180024b13  jz      loc_18002490A
0x180024b19  test    byte ptr [rcx+1Ch], 1
0x180024b1d  jz      loc_18002490A
0x180024b23  mov     edx, 1Bh
0x180024b28  jmp     loc_180024A38
0x180024b2d  mov     edi, 0Eh
0x180024b32  jmp     loc_18002490A
0x180024b37  mov     rax, [rbp+4Fh+Names]
0x180024b3b  movsxd  rcx, dword ptr [rax+18h]
0x180024b3f  mov     rax, [rbp+4Fh+ReferencedDomains]
0x180024b43  lea     rdx, [rcx+rcx*2]
0x180024b47  mov     rcx, [rax+8]
0x180024b4b  movzx   edi, word ptr [rcx+rdx*8]
0x180024b4f  mov     r15, [rcx+rdx*8+8]
0x180024b54  lea     ecx, [rdi+2]; Size
0x180024b57  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180024b5c  mov     rsi, rax
0x180024b5f  test    rax, rax
0x180024b62  jnz     short loc_180024B6E
0x180024b64  mov     edi, 0Eh
0x180024b69  jmp     loc_18002490A
0x180024b6e  mov     r8, rdi; Size
0x180024b71  mov     rdx, r15; Src
0x180024b74  mov     rcx, rsi; void *
0x180024b77  call    memcpy_0
0x180024b7c  shr     rdi, 1
0x180024b7f  xor     eax, eax
0x180024b81  mov     [rsi+rdi*2], ax
0x180024b85  jmp     loc_18002483E
0x180024b8a  mov     ecx, 8; dwErrCode
0x180024b8f  call    cs:__imp_SetLastError
0x180024b96  nop     dword ptr [rax+rax+00h]
0x180024b9b  mov     edi, 0Eh
0x180024ba0  jmp     loc_18002490A
0x180024ba5  mov     [r12], r14
0x180024ba9  xor     r14d, r14d
0x180024bac  jmp     loc_1800248F7
0x180024bb1  mov     [r13+0], rsi
0x180024bb5  xor     esi, esi
0x180024bb7  jmp     loc_180024900
0x180024bbc  mov     rcx, r14
0x180024bbf  call    UBPM_MIDL_user_free
0x180024bc4  jmp     loc_18002496D
0x180024bc9  mov     rcx, rsi
0x180024bcc  call    UBPM_MIDL_user_free
0x180024bd1  jmp     loc_18002497E
0x180024bd6  mov     rcx, rbx
0x180024bd9  call    UBPM_MIDL_user_free
0x180024bde  jmp     loc_18002498F
```
