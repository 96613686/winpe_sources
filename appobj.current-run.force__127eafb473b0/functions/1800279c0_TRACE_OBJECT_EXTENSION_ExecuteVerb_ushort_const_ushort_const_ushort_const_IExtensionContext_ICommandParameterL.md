# TRACE_OBJECT_EXTENSION::ExecuteVerb(ushort const *,ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)

- ea: `0x1800279c0`
- end: `0x180027cb7`
- name: `?ExecuteVerb@TRACE_OBJECT_EXTENSION@@UEAAJPEBG00PEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z`
- size: `759`
- prototype: `__int64 __usercall@<rax>(TRACE_OBJECT_EXTENSION *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, struct IExtensionContext *, struct ICommandParameterList *, struct ICommandObjectList *, struct IXMLDOMDocument *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180025fe4`
- `0x1800279c0`
- `0x180028c60`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180027a43`
- `msvcrt!_wcsicmp` at `0x180027a80`
- `msvcrt!_wcsicmp` at `0x180027ac6`
- `msvcrt!_wcsicmp` at `0x180027a43`
- `msvcrt!_wcsicmp` at `0x180027a80`
- `msvcrt!_wcsicmp` at `0x180027ac6`

## string_xrefs

- `0x180027a76`: `CONFIGURE`

## pseudocode

```c
__int64 __fastcall TRACE_OBJECT_EXTENSION::ExecuteVerb(
        TRACE_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct IExtensionContext *a5,
        struct ICommandParameterList *a6,
        struct ICommandObjectList *a7,
        struct IXMLDOMDocument *a8)
{
  __int64 v11; // rdi
  struct IExtensionContext *v12; // rsi
  struct ICommandParameterList *v13; // r15
  struct ICommandObjectList *v14; // r12
  int v15; // eax
  unsigned int v16; // r14d
  int v17; // ebx
  unsigned __int16 *v18; // r8
  int v19; // eax
  __int64 v20; // rax
  TRACE_OBJECT *v21; // r13
  unsigned int v22; // r13d
  TRACE_OBJECT *v23; // rdi
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rax
  TRACE_OBJECT *v29; // [rsp+40h] [rbp-20h] BYREF
  __int128 v30; // [rsp+48h] [rbp-18h] BYREF
  int v31; // [rsp+A8h] [rbp+48h] BYREF
  unsigned __int16 *v32; // [rsp+B8h] [rbp+58h] BYREF

  v32 = a4;
  v29 = 0;
  v31 = 0;
  v11 = 0;
  v30 = 0;
  if ( !a2 || !a3 || !a4 || (v12 = a5) == 0 || (v13 = a6) == 0 || (v14 = a7) == 0 )
  {
    v17 = -2147024809;
    goto LABEL_34;
  }
  if ( !_wcsicmp(a3, L"LIST") )
  {
    v15 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, unsigned __int16 *, struct ICommandParameterList *, struct ICommandObjectList *, _DWORD))(*(_QWORD *)v12 + 56LL))(
            v12,
            a2,
            v32,
            v13,
            v14,
            0);
    goto LABEL_11;
  }
  v16 = 0;
  if ( !_wcsicmp(a3, L"CONFIGURE") )
  {
    v15 = TRACE_OBJECT_EXTENSION::Configure(this, v12, v32, v13, v14, a8);
LABEL_11:
    v17 = v15;
    if ( v15 < 0 )
      goto LABEL_34;
    goto LABEL_32;
  }
  if ( _wcsicmp(a3, L"INSPECT") )
  {
    v17 = -2147024846;
LABEL_32:
    v11 = 0;
    goto LABEL_34;
  }
  v18 = v32;
  if ( !*v32 )
  {
    v19 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v13 + 40LL))(
            v13,
            L"TRACE.NAME",
            &v32);
    v17 = v19;
    if ( v19 == -2147023483 )
    {
      v20 = *(_QWORD *)v12;
      *(_QWORD *)&v30 = L"TRACE";
      v17 = -2147024846;
      *((_QWORD *)&v30 + 1) = L"TRACE.NAME";
      (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, __int128 *, _DWORD))(v20 + 144))(
        v12,
        2147942450LL,
        3221226474LL,
        &v30,
        0);
      goto LABEL_34;
    }
    if ( v19 < 0 )
      goto LABEL_34;
    v18 = v32;
  }
  v17 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, unsigned __int16 *, TRACE_OBJECT **, _DWORD))(*(_QWORD *)v12 + 64LL))(
          v12,
          L"TRACE",
          v18,
          &v29,
          0);
  if ( v17 >= 0 )
  {
    v21 = v29;
    v17 = TRACE_OBJECT::InitializeTraceEvents(v29);
    if ( v17 >= 0 )
    {
      v22 = *((_DWORD *)v21 + 60);
      while ( v16 < v22 )
      {
        v23 = v29;
        v17 = TRACE_OBJECT::InitializeTraceEvents(v29);
        if ( v17 < 0 )
        {
          v11 = 0;
          goto LABEL_34;
        }
        if ( v16 > *((_DWORD *)v23 + 60) )
        {
          v11 = 0;
          v17 = -2147023483;
          goto LABEL_34;
        }
        v24 = *(_QWORD *)(*((_QWORD *)v23 + 29) + 8LL * v16);
        v25 = v24 - 216;
        v26 = -v24;
        v11 = v25 & -(__int64)(v26 != 0);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 8LL))(v11, v26);
        v27 = *(_QWORD *)v12;
        v31 = 0;
        v17 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, struct ICommandParameterList *, int *))(v27 + 152))(
                v12,
                v11,
                v13,
                &v31);
        if ( v17 < 0 )
          goto LABEL_34;
        if ( v31 )
        {
          v17 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, __int64))(*(_QWORD *)v14 + 24LL))(v14, v11);
          if ( v17 < 0 )
            goto LABEL_34;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        ++v16;
      }
      goto LABEL_32;
    }
  }
LABEL_34:
  if ( v29 )
  {
    (*(void (__fastcall **)(TRACE_OBJECT *))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800279c0  mov     [rsp-38h+arg_0], rbx
0x1800279c5  mov     [rsp-38h+arg_18], r9
0x1800279ca  push    rbp
0x1800279cb  push    rsi
0x1800279cc  push    rdi
0x1800279cd  push    r12
0x1800279cf  push    r13
0x1800279d1  push    r14
0x1800279d3  push    r15
0x1800279d5  mov     rbp, rsp
0x1800279d8  sub     rsp, 60h
0x1800279dc  mov     r13, rcx
0x1800279df  xorps   xmm0, xmm0
0x1800279e2  xor     ecx, ecx
0x1800279e4  mov     rbx, r8
0x1800279e7  mov     [rbp+var_20], rcx
0x1800279eb  mov     r14, rdx
0x1800279ee  mov     [rbp+arg_8], ecx
0x1800279f1  mov     edi, ecx
0x1800279f3  movups  [rbp+var_18], xmm0
0x1800279f7  test    rdx, rdx
0x1800279fa  jz      loc_180027C69
0x180027a00  test    rbx, rbx
0x180027a03  jz      loc_180027C69
0x180027a09  test    r9, r9
0x180027a0c  jz      loc_180027C69
0x180027a12  mov     rsi, [rbp+arg_20]
0x180027a16  test    rsi, rsi
0x180027a19  jz      loc_180027C69
0x180027a1f  mov     r15, [rbp+arg_28]
0x180027a23  test    r15, r15
0x180027a26  jz      loc_180027C69
0x180027a2c  mov     r12, [rbp+arg_30]
0x180027a30  test    r12, r12
0x180027a33  jz      loc_180027C69
0x180027a39  lea     rdx, aList; "LIST"
0x180027a40  mov     rcx, rbx; String1
0x180027a43  call    cs:__imp__wcsicmp
0x180027a49  xor     ecx, ecx
0x180027a4b  test    eax, eax
0x180027a4d  jnz     short loc_180027A76
0x180027a4f  mov     rax, [rsi]
0x180027a52  mov     r9, r15
0x180027a55  mov     r8, [rbp+arg_18]
0x180027a59  mov     rdx, r14
0x180027a5c  mov     dword ptr [rsp+60h+var_38], ecx
0x180027a60  mov     rcx, rsi
0x180027a63  mov     [rsp+60h+var_40], r12
0x180027a68  mov     rax, [rax+38h]
0x180027a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a71  xor     r14d, r14d
0x180027a74  jmp     short loc_180027AAD
0x180027a76  lea     rdx, aConfigure_0; "CONFIGURE"
0x180027a7d  mov     rcx, rbx; String1
0x180027a80  call    cs:__imp__wcsicmp
0x180027a86  xor     r14d, r14d
0x180027a89  test    eax, eax
0x180027a8b  jnz     short loc_180027ABC
0x180027a8d  mov     rax, [rbp+arg_38]
0x180027a91  mov     r9, r15; struct ICommandParameterList *
0x180027a94  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x180027a98  mov     rdx, rsi; struct IExtensionContext *
0x180027a9b  mov     [rsp+60h+var_38], rax; struct IXMLDOMDocument *
0x180027aa0  mov     rcx, r13; this
0x180027aa3  mov     [rsp+60h+var_40], r12; struct ICommandObjectList *
0x180027aa8  call    ?Configure@TRACE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z; TRACE_OBJECT_EXTENSION::Configure(IExtensionContext *,ushort const *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)
0x180027aad  mov     ebx, eax
0x180027aaf  test    eax, eax
0x180027ab1  js      loc_180027C6E
0x180027ab7  jmp     loc_180027C64
0x180027abc  lea     rdx, aInspect; "INSPECT"
0x180027ac3  mov     rcx, rbx; String1
0x180027ac6  call    cs:__imp__wcsicmp
0x180027acc  test    eax, eax
0x180027ace  jnz     loc_180027C5A
0x180027ad4  mov     r8, [rbp+arg_18]
0x180027ad8  cmp     [r8], r14w
0x180027adc  jnz     short loc_180027B4C
0x180027ade  mov     rax, [r15]
0x180027ae1  lea     r13, aTraceName; "TRACE.NAME"
0x180027ae8  lea     r8, [rbp+arg_18]
0x180027aec  mov     rdx, r13
0x180027aef  mov     rcx, r15
0x180027af2  mov     rax, [rax+28h]
0x180027af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027afb  mov     ebx, eax
0x180027afd  cmp     eax, 80070585h
0x180027b02  jnz     short loc_180027B40
0x180027b04  mov     rax, [rsi]
0x180027b07  lea     rdx, aTrace; "TRACE"
0x180027b0e  mov     qword ptr [rbp+var_18], rdx
0x180027b12  lea     r9, [rbp+var_18]
0x180027b16  mov     ebx, 80070032h
0x180027b1b  mov     qword ptr [rbp+var_18+8], r13
0x180027b1f  mov     r8d, 0C00003EAh
0x180027b25  mov     dword ptr [rsp+60h+var_40], r14d
0x180027b2a  mov     rax, [rax+90h]
0x180027b31  mov     edx, ebx
0x180027b33  mov     rcx, rsi
0x180027b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b3b  jmp     loc_180027C6E
0x180027b40  test    eax, eax
0x180027b42  js      loc_180027C6E
0x180027b48  mov     r8, [rbp+arg_18]
0x180027b4c  mov     rax, [rsi]
0x180027b4f  lea     r9, [rbp+var_20]
0x180027b53  lea     rdx, aTrace; "TRACE"
0x180027b5a  mov     dword ptr [rsp+60h+var_40], r14d
0x180027b5f  mov     rcx, rsi
0x180027b62  mov     rax, [rax+40h]
0x180027b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b6b  mov     ebx, eax
0x180027b6d  test    eax, eax
0x180027b6f  js      loc_180027C6E
0x180027b75  mov     r13, [rbp+var_20]
0x180027b79  mov     rcx, r13; this
0x180027b7c  call    ?InitializeTraceEvents@TRACE_OBJECT@@AEAAJXZ; TRACE_OBJECT::InitializeTraceEvents(void)
0x180027b81  mov     ebx, eax
0x180027b83  test    eax, eax
0x180027b85  js      loc_180027C6E
0x180027b8b  mov     r13d, [r13+0F0h]
0x180027b92  cmp     r14d, r13d
0x180027b95  jnb     loc_180027C61
0x180027b9b  mov     rdi, [rbp+var_20]
0x180027b9f  mov     rcx, rdi; this
0x180027ba2  call    ?InitializeTraceEvents@TRACE_OBJECT@@AEAAJXZ; TRACE_OBJECT::InitializeTraceEvents(void)
0x180027ba7  xor     ecx, ecx
0x180027ba9  mov     ebx, eax
0x180027bab  test    eax, eax
0x180027bad  js      loc_180027C55
0x180027bb3  cmp     r14d, [rdi+0F0h]
0x180027bba  ja      loc_180027C4B
0x180027bc0  mov     rax, [rdi+0E8h]
0x180027bc7  mov     ecx, r14d
0x180027bca  mov     rdx, [rax+rcx*8]
0x180027bce  lea     rax, [rdx-0D8h]
0x180027bd5  neg     rdx
0x180027bd8  sbb     rdi, rdi
0x180027bdb  and     rdi, rax
0x180027bde  mov     rcx, rdi
0x180027be1  mov     rax, [rdi]
0x180027be4  mov     rax, [rax+8]
0x180027be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bed  mov     rax, [rsi]
0x180027bf0  lea     r9, [rbp+arg_8]
0x180027bf4  xor     ecx, ecx
0x180027bf6  mov     r8, r15
0x180027bf9  mov     [rbp+arg_8], ecx
0x180027bfc  mov     rdx, rdi
0x180027bff  mov     rcx, rsi
0x180027c02  mov     rax, [rax+98h]
0x180027c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c0e  mov     ebx, eax
0x180027c10  xor     eax, eax
0x180027c12  test    ebx, ebx
0x180027c14  js      short loc_180027C6E
0x180027c16  cmp     [rbp+arg_8], eax
0x180027c19  jz      short loc_180027C34
0x180027c1b  mov     rax, [r12]
0x180027c1f  mov     rdx, rdi
0x180027c22  mov     rcx, r12
0x180027c25  mov     rax, [rax+18h]
0x180027c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c2e  mov     ebx, eax
0x180027c30  test    eax, eax
0x180027c32  js      short loc_180027C6E
0x180027c34  mov     rax, [rdi]
0x180027c37  mov     rcx, rdi
0x180027c3a  mov     rax, [rax+10h]
0x180027c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c43  inc     r14d
0x180027c46  jmp     loc_180027B92
0x180027c4b  mov     rdi, rcx
0x180027c4e  mov     ebx, 80070585h
0x180027c53  jmp     short loc_180027C6E
0x180027c55  mov     rdi, rcx
0x180027c58  jmp     short loc_180027C6E
0x180027c5a  mov     ebx, 80070032h
0x180027c5f  jmp     short loc_180027C64
0x180027c61  xor     r14d, r14d
0x180027c64  mov     rdi, r14
0x180027c67  jmp     short loc_180027C6E
0x180027c69  mov     ebx, 80070057h
0x180027c6e  mov     rcx, [rbp+var_20]
0x180027c72  xor     esi, esi
0x180027c74  test    rcx, rcx
0x180027c77  jz      short loc_180027C89
0x180027c79  mov     rax, [rcx]
0x180027c7c  mov     rax, [rax+10h]
0x180027c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c85  mov     [rbp+var_20], rsi
0x180027c89  test    rdi, rdi
0x180027c8c  jz      short loc_180027C9D
0x180027c8e  mov     rax, [rdi]
0x180027c91  mov     rcx, rdi
0x180027c94  mov     rax, [rax+10h]
0x180027c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c9d  mov     eax, ebx
0x180027c9f  mov     rbx, [rsp+60h+arg_0]
0x180027ca7  add     rsp, 60h
0x180027cab  pop     r15
0x180027cad  pop     r14
0x180027caf  pop     r13
0x180027cb1  pop     r12
0x180027cb3  pop     rdi
0x180027cb4  pop     rsi
0x180027cb5  pop     rbp
0x180027cb6  retn
```
