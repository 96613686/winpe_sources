# CCompositionSurfaceManager::GetOrCreateCompositionSurfaceInfo(void *,CCompositionSurfaceInfo * *)

- ea: `0x18002d150`
- end: `0x18002d2c6`
- name: `?GetOrCreateCompositionSurfaceInfo@CCompositionSurfaceManager@@QEAAJPEAXPEAPEAVCCompositionSurfaceInfo@@@Z`
- size: `374`
- prototype: `int(CCompositionSurfaceManager *__hidden this, void *, struct CCompositionSurfaceInfo **)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002d710`
- `0x1801d4188`

## callees

- `0x18002ce20`
- `0x18002d150`
- `0x180042de0`
- `0x1800c677c`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d202`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d202`
- `ntdll!RtlLookupElementGenericTable` at `0x18002d1cc`
- `ntdll!RtlLookupElementGenericTable` at `0x18002d1cc`
- `win32u!NtValidateCompositionSurfaceHandle` at `0x18002d182`
- `win32u!NtValidateCompositionSurfaceHandle` at `0x18002d182`

## pseudocode

```c
__int64 __fastcall CCompositionSurfaceManager::GetOrCreateCompositionSurfaceInfo(
        CCompositionSurfaceManager *this,
        void *a2,
        struct CCompositionSurfaceInfo **a3)
{
  int v6; // eax
  int v7; // ebx
  struct IVtrSurfaceManager *VtrSurfaceManager; // rax
  struct CCompositionSurfaceInfo *v9; // rdi
  PVOID v10; // rax
  char v11; // si
  int v13; // eax
  _QWORD Buffer[5]; // [rsp+30h] [rbp-28h] BYREF
  struct _LUID v15; // [rsp+70h] [rbp+18h] BYREF
  struct CCompositionSurfaceInfo *v16; // [rsp+78h] [rbp+20h] BYREF

  v15 = 0;
  *a3 = 0;
  v6 = NtValidateCompositionSurfaceHandle(a2, &v15);
  if ( v6 < 0 )
  {
    v7 = v6 | 0x10000000;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v6 | 0x10000000, 0x36u, 0);
  }
  else
  {
    v7 = 0;
    VtrSurfaceManager = TryGetVtrSurfaceManager();
    if ( VtrSurfaceManager )
    {
      (*(void (__fastcall **)(struct IVtrSurfaceManager *, void *, struct _LUID *))(*(_QWORD *)VtrSurfaceManager + 40LL))(
        VtrSurfaceManager,
        a2,
        &v15);
      goto LABEL_4;
    }
  }
  if ( v7 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v7, 0x36u, 0);
    return (unsigned int)v7;
  }
LABEL_4:
  v9 = 0;
  Buffer[0] = v15;
  Buffer[1] = 0;
  v10 = RtlLookupElementGenericTable((PRTL_GENERIC_TABLE)((char *)this + 8), Buffer);
  if ( v10 )
    v9 = (struct CCompositionSurfaceInfo *)*((_QWORD *)v10 + 1);
  v16 = v9;
  if ( v9 )
  {
    v11 = 1;
    (*(void (__fastcall **)(struct CCompositionSurfaceInfo *))(*(_QWORD *)v9 + 8LL))(v9);
  }
  else
  {
    v13 = CCompositionSurfaceInfo::Create(a2, v15, this, &v16);
    v7 = v13;
    if ( v13 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v13, 0x46u, 0);
      goto LABEL_9;
    }
    v9 = v16;
    v11 = 0;
  }
  *a3 = v9;
  if ( v11 )
LABEL_9:
    CloseHandle(a2);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002d150  mov     rax, rsp
0x18002d153  mov     [rax+8], rbx
0x18002d157  mov     [rax+10h], rbp
0x18002d15b  push    rsi
0x18002d15c  push    rdi
0x18002d15d  push    r14
0x18002d15f  sub     rsp, 40h
0x18002d163  mov     rbp, rdx
0x18002d166  mov     qword ptr [rax+18h], 0
0x18002d16e  mov     rsi, rcx
0x18002d171  mov     qword ptr [r8], 0
0x18002d178  mov     rcx, rbp
0x18002d17b  lea     rdx, [rax+18h]
0x18002d17f  mov     r14, r8
0x18002d182  call    cs:__imp_NtValidateCompositionSurfaceHandle
0x18002d188  mov     ebx, eax
0x18002d18a  mov     edi, 36h ; '6'
0x18002d18f  test    eax, eax
0x18002d191  js      loc_18002D284
0x18002d197  xor     ebx, ebx
0x18002d199  call    ?TryGetVtrSurfaceManager@@YAPEAVIVtrSurfaceManager@@XZ; TryGetVtrSurfaceManager(void)
0x18002d19e  mov     r9, rax
0x18002d1a1  test    rax, rax
0x18002d1a4  jnz     loc_18002D2AA
0x18002d1aa  test    ebx, ebx
0x18002d1ac  js      loc_18002D265
0x18002d1b2  mov     rax, qword ptr [rsp+58h+arg_10.LowPart]
0x18002d1b7  lea     rcx, [rsi+8]; Table
0x18002d1bb  xor     edi, edi
0x18002d1bd  mov     [rsp+58h+Buffer], rax
0x18002d1c2  lea     rdx, [rsp+58h+Buffer]; Buffer
0x18002d1c7  mov     [rsp+58h+var_20], rdi
0x18002d1cc  call    cs:__imp_RtlLookupElementGenericTable
0x18002d1d2  test    rax, rax
0x18002d1d5  jz      short loc_18002D1DB
0x18002d1d7  mov     rdi, [rax+8]
0x18002d1db  mov     [rsp+58h+arg_18], rdi
0x18002d1e0  test    rdi, rdi
0x18002d1e3  jz      short loc_18002D21D
0x18002d1e5  mov     rax, [rdi]
0x18002d1e8  mov     rcx, rdi
0x18002d1eb  mov     sil, 1
0x18002d1ee  mov     rax, [rax+8]
0x18002d1f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1f7  mov     [r14], rdi
0x18002d1fa  test    sil, sil
0x18002d1fd  jz      short loc_18002D208
0x18002d1ff  mov     rcx, rbp; hObject
0x18002d202  call    cs:__imp_CloseHandle
0x18002d208  mov     rbp, [rsp+58h+arg_8]
0x18002d20d  mov     eax, ebx
0x18002d20f  mov     rbx, [rsp+58h+arg_0]
0x18002d214  add     rsp, 40h
0x18002d218  pop     r14
0x18002d21a  pop     rdi
0x18002d21b  pop     rsi
0x18002d21c  retn
0x18002d21d  mov     rdx, qword ptr [rsp+58h+arg_10.LowPart]; struct _LUID
0x18002d222  lea     r9, [rsp+58h+arg_18]; struct CCompositionSurfaceInfo **
0x18002d227  mov     r8, rsi; struct CCompositionSurfaceManager *
0x18002d22a  mov     rcx, rbp; void *
0x18002d22d  call    ?Create@CCompositionSurfaceInfo@@SAJPEAXU_LUID@@PEAVCCompositionSurfaceManager@@PEAPEAV1@@Z; CCompositionSurfaceInfo::Create(void *,_LUID,CCompositionSurfaceManager *,CCompositionSurfaceInfo * *)
0x18002d232  mov     ebx, eax
0x18002d234  test    eax, eax
0x18002d236  js      short loc_18002D242
0x18002d238  mov     rdi, [rsp+58h+arg_18]
0x18002d23d  xor     sil, sil
0x18002d240  jmp     short loc_18002D1F7
0x18002d242  xor     edx, edx; int *
0x18002d244  mov     [rsp+58h+var_30], 0; void *
0x18002d24d  mov     r9d, eax; int
0x18002d250  mov     [rsp+58h+var_38], 46h ; 'F'; unsigned int
0x18002d258  xor     r8d, r8d; unsigned int
0x18002d25b  lea     ecx, [rdx+14h]; unsigned int
0x18002d25e  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18002d263  jmp     short loc_18002D1FF
0x18002d265  xor     edx, edx; int *
0x18002d267  mov     [rsp+58h+var_30], 0; void *
0x18002d270  mov     r9d, ebx; int
0x18002d273  mov     [rsp+58h+var_38], edi; unsigned int
0x18002d277  xor     r8d, r8d; unsigned int
0x18002d27a  lea     ecx, [rdx+14h]; unsigned int
0x18002d27d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18002d282  jmp     short loc_18002D208
0x18002d284  xor     edx, edx; int *
0x18002d286  mov     [rsp+58h+var_30], 0; void *
0x18002d28f  bts     ebx, 1Ch
0x18002d293  mov     [rsp+58h+var_38], edi; unsigned int
0x18002d297  mov     r9d, ebx; int
0x18002d29a  xor     r8d, r8d; unsigned int
0x18002d29d  lea     ecx, [rdx+14h]; unsigned int
0x18002d2a0  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18002d2a5  jmp     loc_18002D1AA
0x18002d2aa  mov     rcx, [rax]
0x18002d2ad  lea     r8, [rsp+58h+arg_10]
0x18002d2b2  mov     rdx, rbp
0x18002d2b5  mov     rax, [rcx+28h]
0x18002d2b9  mov     rcx, r9
0x18002d2bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2c1  jmp     loc_18002D1B2
```
