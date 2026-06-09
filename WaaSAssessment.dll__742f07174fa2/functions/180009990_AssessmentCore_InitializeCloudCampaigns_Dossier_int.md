# AssessmentCore::InitializeCloudCampaigns(Dossier * *,int)

- ea: `0x180009990`
- end: `0x180009a39`
- name: `?InitializeCloudCampaigns@AssessmentCore@@MEAAJPEAPEAVDossier@@H@Z`
- size: `169`
- prototype: `__int64 __fastcall(AssessmentCore *__hidden this, struct Dossier **, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002f58`
- `0x180009990`
- `0x18001752c`
- `0x18001b010`

## string_xrefs

- `0x180009a14`: `Initializing dossier complete, HRESULT: 0x%08X`

## pseudocode

```c
__int64 __fastcall AssessmentCore::InitializeCloudCampaigns(AssessmentCore *this, struct Dossier **a2, unsigned int a3)
{
  _QWORD *v5; // rax
  int v6; // eax
  unsigned int v7; // ebx

  LogLevel(4u, L"Initializing Cloud Campaigns ...");
  v5 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v5 )
    return 2147942414LL;
  v5[1] = 0;
  *v5 = &Dossier::`vftable';
  *((_DWORD *)v5 + 4) = 0;
  *a2 = (struct Dossier *)v5;
  v6 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, _QWORD, _QWORD, _DWORD))(*v5 + 24LL))(
         v5,
         L"RUXIM",
         0,
         a3,
         0);
  v7 = v6;
  if ( v6 < 0 )
    LogLevel(5u, L"Initializing dossier complete, HRESULT: 0x%08X", (unsigned int)v6);
  return v7;
}

```

## disassembly

```asm
0x180009990  mov     [rsp+arg_0], rbx
0x180009995  push    rdi
0x180009996  sub     rsp, 30h
0x18000999a  mov     rdi, rdx
0x18000999d  mov     ecx, 4; unsigned __int8
0x1800099a2  lea     rdx, aInitializingCl; "Initializing Cloud Campaigns ..."
0x1800099a9  mov     ebx, r8d
0x1800099ac  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x1800099b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800099b8  mov     ecx, 18h; unsigned __int64
0x1800099bd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800099c2  mov     r10, rax
0x1800099c5  test    rax, rax
0x1800099c8  jz      short loc_180009A29
0x1800099ca  mov     qword ptr [r10+8], 0
0x1800099d2  lea     rax, ??_7Dossier@@6B@; const Dossier::`vftable'
0x1800099d9  mov     [r10], rax
0x1800099dc  lea     rdx, aRuxim; "RUXIM"
0x1800099e3  mov     dword ptr [r10+10h], 0
0x1800099eb  mov     r9d, ebx
0x1800099ee  mov     [rdi], r10
0x1800099f1  xor     r8d, r8d
0x1800099f4  mov     rcx, [r10]
0x1800099f7  mov     [rsp+38h+var_18], 0
0x1800099ff  mov     rax, [rcx+18h]
0x180009a03  mov     rcx, r10
0x180009a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a0b  mov     ebx, eax
0x180009a0d  test    eax, eax
0x180009a0f  jns     short loc_180009A25
0x180009a11  mov     r8d, eax
0x180009a14  lea     rdx, aInitializingDo_0; "Initializing dossier complete, HRESULT:"...
0x180009a1b  mov     ecx, 5; unsigned __int8
0x180009a20  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180009a25  mov     eax, ebx
0x180009a27  jmp     short loc_180009A2E
0x180009a29  mov     eax, 8007000Eh
0x180009a2e  mov     rbx, [rsp+38h+arg_0]
0x180009a33  add     rsp, 30h
0x180009a37  pop     rdi
0x180009a38  retn
```
