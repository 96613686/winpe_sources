# PackageRepository::ExtensionRow::Initialize(__int64,void *,__int64,ushort const *,ushort const *,ushort const *,PackageRepository::ExtensionStatus)

- ea: `0x1801932c0`
- end: `0x180193491`
- name: `?Initialize@ExtensionRow@PackageRepository@@QEAAJ_JPEAX0PEBG22W4ExtensionStatus@2@@Z`
- size: `465`
- prototype: `int __high(__int64, void *, __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, enum PackageRepository::ExtensionStatus)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18017ab60`

## callees

- `0x18001adb4`
- `0x18019325c`
- `0x1801932c0`

## import_xrefs

- `AppxDeploymentServer!PackageRepositoryAllocate` at `0x180193371`
- `AppxDeploymentServer!PackageRepositoryAllocate` at `0x180193371`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x180193387`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x1801933d8`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x1801933f8`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x180193406`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x180193414`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x180193422`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x180193454`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x180193463`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x180193472`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x180193387`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x1801933d8`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x1801933f8`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x180193406`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x180193414`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x180193422`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x180193454`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x180193463`
- `AppxDeploymentServer!PackageRepositoryFree` at `0x180193472`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801933b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801933b7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1801933a7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1801933a7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1801932de`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1801932de`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180193360`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180193360`

## string_xrefs

- `0x180193437`: `onecore\admin\appmodel\packagerepository\common\extensionrow.cpp`

## pseudocode

```c
__int64 __fastcall PackageRepository::ExtensionRow::Initialize(
        __int64 a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        PackageRepository *a5,
        PackageRepository *a6,
        PackageRepository *a7,
        int a8)
{
  const unsigned __int16 *v12; // rdx
  unsigned __int16 *v14; // rbp
  const unsigned __int16 *v15; // rdx
  unsigned __int16 *v16; // rdi
  const unsigned __int16 *v17; // rdx
  unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // rsi
  DWORD LengthSid; // r12d
  void *v21; // rax
  void *v22; // rbx
  unsigned int v23; // r14d
  signed int LastError; // eax
  int v25; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !IsValidSid(a3) )
    return 2147943737LL;
  *(_DWORD *)(a1 + 48) = a8;
  *(_QWORD *)a1 = a2;
  *(_QWORD *)(a1 + 16) = a4;
  v14 = PackageRepository::Duplicate(a5, v12);
  v16 = PackageRepository::Duplicate(a6, v15);
  v18 = PackageRepository::Duplicate(a7, v17);
  v19 = v18;
  if ( v14 && v18 && (v16 || !a6) )
  {
    LengthSid = GetLengthSid(a3);
    v21 = PackageRepositoryAllocate(LengthSid);
    v22 = v21;
    if ( v21 )
    {
      if ( CopySid(LengthSid, v21, a3) )
      {
        *(_QWORD *)(a1 + 24) = v14;
        *(_QWORD *)(a1 + 32) = v16;
        *(_QWORD *)(a1 + 40) = v19;
        *(_QWORD *)(a1 + 8) = v22;
        PackageRepositoryFree(0);
        PackageRepositoryFree(0);
        PackageRepositoryFree(0);
        PackageRepositoryFree(0);
        return 0;
      }
      LastError = GetLastError();
      v23 = LastError;
      if ( LastError > 0 )
        v23 = (unsigned __int16)LastError | 0x80070000;
      PackageRepositoryFree(v22);
    }
    else
    {
      PackageRepositoryFree(0);
      v23 = -2147024882;
    }
  }
  else
  {
    v23 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecore\\admin\\appmodel\\packagerepository\\common\\extensionrow.cpp",
      (const char *)0x8007000ELL,
      v25);
  }
  PackageRepositoryFree(v19);
  PackageRepositoryFree(v16);
  PackageRepositoryFree(v14);
  return v23;
}

```

## disassembly

```asm
0x1801932c0  push    rbx
0x1801932c2  push    rbp
0x1801932c3  push    rsi
0x1801932c4  push    rdi
0x1801932c5  push    r12
0x1801932c7  push    r14
0x1801932c9  push    r15; int
0x1801932cb  sub     rsp, 20h
0x1801932cf  mov     r14, rcx
0x1801932d2  mov     rbx, r9
0x1801932d5  mov     rcx, r8; pSid
0x1801932d8  mov     r15, r8
0x1801932db  mov     rdi, rdx
0x1801932de  call    cs:__imp_IsValidSid
0x1801932e5  nop     dword ptr [rax+rax+00h]
0x1801932ea  test    eax, eax
0x1801932ec  jnz     short loc_1801932F8
0x1801932ee  mov     eax, 80070539h
0x1801932f3  jmp     loc_180193481
0x1801932f8  mov     eax, [rsp+58h+arg_38]
0x1801932ff  mov     rcx, [rsp+58h+arg_20]; this
0x180193307  mov     [r14+30h], eax
0x18019330b  mov     [r14], rdi
0x18019330e  mov     [r14+10h], rbx
0x180193312  call    ?Duplicate@PackageRepository@@YAPEAGPEBG@Z; PackageRepository::Duplicate(ushort const *)
0x180193317  mov     rbx, [rsp+58h+arg_28]
0x18019331f  mov     rbp, rax
0x180193322  mov     rcx, rbx; this
0x180193325  call    ?Duplicate@PackageRepository@@YAPEAGPEBG@Z; PackageRepository::Duplicate(ushort const *)
0x18019332a  mov     rcx, [rsp+58h+arg_30]; this
0x180193332  mov     rdi, rax
0x180193335  call    ?Duplicate@PackageRepository@@YAPEAGPEBG@Z; PackageRepository::Duplicate(ushort const *)
0x18019333a  mov     rsi, rax
0x18019333d  test    rbp, rbp
0x180193340  jz      loc_180193432
0x180193346  test    rax, rax
0x180193349  jz      loc_180193432
0x18019334f  test    rdi, rdi
0x180193352  jnz     short loc_18019335D
0x180193354  test    rbx, rbx
0x180193357  jnz     loc_180193432
0x18019335d  mov     rcx, r15; pSid
0x180193360  call    cs:__imp_GetLengthSid
0x180193367  nop     dword ptr [rax+rax+00h]
0x18019336c  mov     ecx, eax
0x18019336e  mov     r12d, eax
0x180193371  call    cs:__imp_?PackageRepositoryAllocate@@YAPEAX_K@Z; PackageRepositoryAllocate(unsigned __int64)
0x180193378  nop     dword ptr [rax+rax+00h]
0x18019337d  mov     rbx, rax
0x180193380  test    rax, rax
0x180193383  jnz     short loc_18019339E
0x180193385  xor     ecx, ecx
0x180193387  call    cs:__imp_?PackageRepositoryFree@@YAXPEAX@Z; PackageRepositoryFree(void *)
0x18019338e  nop     dword ptr [rax+rax+00h]
0x180193393  mov     r14d, 8007000Eh
0x180193399  jmp     loc_180193451
0x18019339e  mov     r8, r15; pSourceSid
0x1801933a1  mov     rdx, rbx; pDestinationSid
0x1801933a4  mov     ecx, r12d; nDestinationSidLength
0x1801933a7  call    cs:__imp_CopySid
0x1801933ae  nop     dword ptr [rax+rax+00h]
0x1801933b3  test    eax, eax
0x1801933b5  jnz     short loc_1801933E6
0x1801933b7  call    cs:__imp_GetLastError
0x1801933be  nop     dword ptr [rax+rax+00h]
0x1801933c3  mov     r14d, eax
0x1801933c6  test    eax, eax
0x1801933c8  jle     short loc_1801933D5
0x1801933ca  movzx   r14d, ax
0x1801933ce  or      r14d, 80070000h
0x1801933d5  mov     rcx, rbx
0x1801933d8  call    cs:__imp_?PackageRepositoryFree@@YAXPEAX@Z; PackageRepositoryFree(void *)
0x1801933df  nop     dword ptr [rax+rax+00h]
0x1801933e4  jmp     short loc_180193451
0x1801933e6  xor     ecx, ecx
0x1801933e8  mov     [r14+18h], rbp
0x1801933ec  mov     [r14+20h], rdi
0x1801933f0  mov     [r14+28h], rsi
0x1801933f4  mov     [r14+8], rbx
0x1801933f8  call    cs:__imp_?PackageRepositoryFree@@YAXPEAX@Z; PackageRepositoryFree(void *)
0x1801933ff  nop     dword ptr [rax+rax+00h]
0x180193404  xor     ecx, ecx
0x180193406  call    cs:__imp_?PackageRepositoryFree@@YAXPEAX@Z; PackageRepositoryFree(void *)
0x18019340d  nop     dword ptr [rax+rax+00h]
0x180193412  xor     ecx, ecx
0x180193414  call    cs:__imp_?PackageRepositoryFree@@YAXPEAX@Z; PackageRepositoryFree(void *)
0x18019341b  nop     dword ptr [rax+rax+00h]
0x180193420  xor     ecx, ecx
0x180193422  call    cs:__imp_?PackageRepositoryFree@@YAXPEAX@Z; PackageRepositoryFree(void *)
0x180193429  nop     dword ptr [rax+rax+00h]
0x18019342e  xor     eax, eax
0x180193430  jmp     short loc_180193481
0x180193432  mov     rcx, [rsp+58h]; this
0x180193437  lea     r8, aOnecoreAdminAp_73; "onecore\\admin\\appmodel\\packagereposi"...
0x18019343e  mov     r14d, 8007000Eh
0x180193444  mov     edx, 25h ; '%'; void *
0x180193449  mov     r9d, r14d; char *
0x18019344c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180193451  mov     rcx, rsi
0x180193454  call    cs:__imp_?PackageRepositoryFree@@YAXPEAX@Z; PackageRepositoryFree(void *)
0x18019345b  nop     dword ptr [rax+rax+00h]
0x180193460  mov     rcx, rdi
0x180193463  call    cs:__imp_?PackageRepositoryFree@@YAXPEAX@Z; PackageRepositoryFree(void *)
0x18019346a  nop     dword ptr [rax+rax+00h]
0x18019346f  mov     rcx, rbp
0x180193472  call    cs:__imp_?PackageRepositoryFree@@YAXPEAX@Z; PackageRepositoryFree(void *)
0x180193479  nop     dword ptr [rax+rax+00h]
0x18019347e  mov     eax, r14d
0x180193481  add     rsp, 20h
0x180193485  pop     r15
0x180193487  pop     r14
0x180193489  pop     r12
0x18019348b  pop     rdi
0x18019348c  pop     rsi
0x18019348d  pop     rbp
0x18019348e  pop     rbx
0x18019348f  retn
```
