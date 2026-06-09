# CRsopContext::GetRsopNamespaceKeyPath(void *,ushort * *)

- ea: `0x1800297b4`
- end: `0x1800298ec`
- name: `?GetRsopNamespaceKeyPath@CRsopContext@@QEAAJPEAXPEAPEAG@Z`
- size: `312`
- prototype: `__int64 __fastcall(CRsopContext *this, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800298f4`

## callees

- `0x180002aa0`
- `0x18000cc10`
- `0x1800297b4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029877`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029877`
- `ntdll!RtlFreeUnicodeString` at `0x1800298d5`
- `ntdll!RtlFreeUnicodeString` at `0x1800298d5`
- `ntdll!RtlNtStatusToDosError` at `0x180029811`
- `ntdll!RtlNtStatusToDosError` at `0x180029811`
- `ntdll!RtlInitUnicodeString` at `0x1800297e1`
- `ntdll!RtlInitUnicodeString` at `0x1800297e1`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800297fe`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800297fe`

## string_xrefs

- `0x1800298a6`: `\Extension-List\`

## pseudocode

```c
__int64 __fastcall CRsopContext::GetRsopNamespaceKeyPath(CRsopContext *this, void *a2, unsigned __int16 **a3)
{
  ULONG v6; // ebx
  int v7; // eax
  const unsigned __int16 *Buffer; // rdi
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rax
  unsigned __int64 v12; // rsi
  SIZE_T v13; // rax
  unsigned __int16 *v14; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF

  DestinationString = 0;
  *a3 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v6 = 0;
  if ( a2 )
  {
    v7 = RtlConvertSidToUnicodeString(&DestinationString, a2, 1u);
    if ( v7 < 0 )
    {
      v6 = RtlNtStatusToDosError(v7);
      Buffer = 0;
      if ( v6 )
        goto LABEL_19;
    }
    else
    {
      Buffer = DestinationString.Buffer;
    }
    if ( !Buffer )
    {
      LODWORD(v9) = 0;
      goto LABEL_10;
    }
  }
  else
  {
    Buffer = L"Machine";
  }
  v9 = -1;
  do
    ++v9;
  while ( Buffer[v9] );
LABEL_10:
  v10 = *((_QWORD *)this + 3);
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(v10 + 2 * v11) );
  }
  else
  {
    LODWORD(v11) = 0;
  }
  v12 = (unsigned int)(v9 + v11 + 80);
  v13 = 2 * v12;
  if ( !is_mul_ok(v12, 2u) )
    v13 = -1;
  v14 = (unsigned __int16 *)LocalAlloc(0, v13);
  *a3 = v14;
  if ( v14 )
  {
    StringCchCopyW(v14, (unsigned int)v12, L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\State\\");
    StringCchCatW(*a3, (unsigned int)v12, Buffer);
    StringCchCatW(*a3, (unsigned int)v12, L"\\Extension-List\\");
    StringCchCatW(*a3, (unsigned int)v12, *((const unsigned __int16 **)this + 3));
  }
  else
  {
    v6 = 14;
  }
LABEL_19:
  if ( DestinationString.Buffer )
    RtlFreeUnicodeString(&DestinationString);
  return v6;
}

```

## disassembly

```asm
0x1800297b4  push    rbx
0x1800297b6  push    rbp
0x1800297b7  push    rsi
0x1800297b8  push    rdi
0x1800297b9  push    r12
0x1800297bb  push    r14
0x1800297bd  push    r15
0x1800297bf  sub     rsp, 30h
0x1800297c3  mov     rdi, rdx
0x1800297c6  mov     rbp, rcx
0x1800297c9  xorps   xmm0, xmm0
0x1800297cc  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800297d1  xor     r15d, r15d
0x1800297d4  xor     edx, edx; SourceString
0x1800297d6  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1800297db  mov     [r8], r15
0x1800297de  mov     r14, r8
0x1800297e1  call    cs:__imp_RtlInitUnicodeString
0x1800297e7  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800297eb  mov     ebx, r15d
0x1800297ee  test    rdi, rdi
0x1800297f1  jz      short loc_18002982E
0x1800297f3  mov     r8b, 1; AllocateDestinationString
0x1800297f6  lea     rcx, [rsp+68h+DestinationString]; UnicodeString
0x1800297fb  mov     rdx, rdi; Sid
0x1800297fe  call    cs:__imp_RtlConvertSidToUnicodeString
0x180029804  test    eax, eax
0x180029806  js      short loc_18002980F
0x180029808  mov     rdi, [rsp+68h+DestinationString.Buffer]
0x18002980d  jmp     short loc_180029824
0x18002980f  mov     ecx, eax; Status
0x180029811  call    cs:__imp_RtlNtStatusToDosError
0x180029817  mov     ebx, eax
0x180029819  mov     rdi, r15
0x18002981c  test    eax, eax
0x18002981e  jnz     loc_1800298C9
0x180029824  test    rdi, rdi
0x180029827  jnz     short loc_180029835
0x180029829  mov     rcx, r15
0x18002982c  jmp     short loc_180029842
0x18002982e  lea     rdi, aMachine_0; "Machine"
0x180029835  mov     rcx, r12
0x180029838  inc     rcx
0x18002983b  cmp     [rdi+rcx*2], r15w
0x180029840  jnz     short loc_180029838
0x180029842  mov     rdx, [rbp+18h]
0x180029846  test    rdx, rdx
0x180029849  jnz     short loc_180029850
0x18002984b  mov     rax, r15
0x18002984e  jmp     short loc_18002985D
0x180029850  mov     rax, r12
0x180029853  inc     rax
0x180029856  cmp     [rdx+rax*2], r15w
0x18002985b  jnz     short loc_180029853
0x18002985d  lea     rsi, [rax+50h]
0x180029861  mov     eax, 2
0x180029866  add     rsi, rcx
0x180029869  mov     esi, esi
0x18002986b  mul     rsi
0x18002986e  cmovb   rax, r12
0x180029872  xor     ecx, ecx; uFlags
0x180029874  mov     rdx, rax; uBytes
0x180029877  call    cs:__imp_LocalAlloc
0x18002987d  mov     [r14], rax
0x180029880  test    rax, rax
0x180029883  jz      short loc_1800298C4
0x180029885  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002988c  mov     edx, esi; unsigned __int64
0x18002988e  mov     rcx, rax; unsigned __int16 *
0x180029891  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029896  mov     rcx, [r14]; unsigned __int16 *
0x180029899  mov     r8, rdi; unsigned __int16 *
0x18002989c  mov     edx, esi; unsigned __int64
0x18002989e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800298a3  mov     rcx, [r14]; unsigned __int16 *
0x1800298a6  lea     r8, aExtensionList; "\\Extension-List\\"
0x1800298ad  mov     edx, esi; unsigned __int64
0x1800298af  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800298b4  mov     r8, [rbp+18h]; unsigned __int16 *
0x1800298b8  mov     edx, esi; unsigned __int64
0x1800298ba  mov     rcx, [r14]; unsigned __int16 *
0x1800298bd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800298c2  jmp     short loc_1800298C9
0x1800298c4  mov     ebx, 0Eh
0x1800298c9  cmp     [rsp+68h+DestinationString.Buffer], r15
0x1800298ce  jz      short loc_1800298DB
0x1800298d0  lea     rcx, [rsp+68h+DestinationString]; UnicodeString
0x1800298d5  call    cs:__imp_RtlFreeUnicodeString
0x1800298db  mov     eax, ebx
0x1800298dd  add     rsp, 30h
0x1800298e1  pop     r15
0x1800298e3  pop     r14
0x1800298e5  pop     r12
0x1800298e7  pop     rdi
0x1800298e8  pop     rsi
0x1800298e9  pop     rbp
0x1800298ea  pop     rbx
0x1800298eb  retn
```
