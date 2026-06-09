# Windows::UI::Composition::Visual::OnChildAdded(Windows::UI::Composition::Visual *,Windows::UI::Composition::Visual *,bool)

- ea: `0x180056160`
- end: `0x18005639b`
- name: `?OnChildAdded@Visual@Composition@UI@Windows@@MEAAXPEAV1234@0_N@Z`
- size: `571`
- prototype: `void __fastcall(Windows::UI::Composition::Visual *__hidden this, struct Windows::UI::Composition::Visual *, struct Windows::UI::Composition::Visual *, bool)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800093f4`
- `0x180056160`
- `0x1800563a4`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005628e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005628e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056268`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800562cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005636d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056268`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800562cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005636d`

## pseudocode

```c
void __fastcall Windows::UI::Composition::Visual::OnChildAdded(
        Windows::UI::Composition::Visual *this,
        struct Windows::UI::Composition::Visual *a2,
        struct Windows::UI::Composition::Visual *a3,
        char a4)
{
  char *v6; // rbx
  char *v7; // rdi
  char *v8; // rsi
  char *v9; // r12
  char *v10; // r15
  struct Windows::UI::Composition::Visual *v11; // r14
  HSTRING Reference; // rax
  HSTRING newString; // [rsp+40h] [rbp-20h] BYREF
  char *v14; // [rsp+48h] [rbp-18h] BYREF
  char *v15; // [rsp+50h] [rbp-10h] BYREF
  char *v16; // [rsp+58h] [rbp-8h] BYREF

  if ( Windows::UI::Composition::Visual::s_fIsVisualTreeCallbackRegistered )
  {
    v6 = 0;
    v7 = 0;
    v8 = 0;
    v16 = 0;
    v15 = 0;
    v14 = 0;
    if ( this )
    {
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v16);
      v6 = (char *)this + 184;
      v16 = (char *)this + 184;
      if ( _InterlockedIncrement((volatile signed __int32 *)this + 4) == 1 )
        (*(void (__fastcall **)(Windows::UI::Composition::Visual *))(*(_QWORD *)this + 80LL))(this);
      v9 = (char *)this + 184;
    }
    else
    {
      v9 = 0;
    }
    if ( a2 )
    {
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v15);
      v7 = (char *)a2 + 184;
      v15 = (char *)a2 + 184;
      if ( _InterlockedIncrement((volatile signed __int32 *)a2 + 4) == 1 )
        (*(void (__fastcall **)(struct Windows::UI::Composition::Visual *))(*(_QWORD *)a2 + 80LL))(a2);
      v10 = (char *)a2 + 184;
    }
    else
    {
      v10 = 0;
    }
    v11 = a3;
    if ( a3 )
    {
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v14);
      v8 = (char *)a3 + 184;
      v14 = (char *)a3 + 184;
      if ( _InterlockedIncrement((volatile signed __int32 *)a3 + 4) == 1 )
        (*(void (__fastcall **)(struct Windows::UI::Composition::Visual *))(*(_QWORD *)a3 + 80LL))(a3);
      v11 = (struct Windows::UI::Composition::Visual *)((char *)a3 + 184);
    }
    WindowsDeleteString(0);
    newString = 0;
    Reference = (HSTRING)CSparseStorage::GetReference((struct Windows::UI::Composition::Visual *)((char *)a2 + 128), 1u);
    WindowsDuplicateString(Reference, &newString);
    if ( (*(int (__fastcall **)(__int64, char *, char *, char *, char, HSTRING))(*(_QWORD *)qword_1801E0E40 + 24LL))(
           qword_1801E0E40,
           v7,
           v6,
           v8,
           a4,
           newString) >= 0 )
    {
      WindowsDeleteString(newString);
      newString = 0;
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v14);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v15);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v16);
    }
    else
    {
      WindowsDeleteString(newString);
      newString = 0;
      if ( v11 )
        (*(void (__fastcall **)(struct Windows::UI::Composition::Visual *))(*(_QWORD *)v11 + 16LL))(v11);
      if ( v10 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
      if ( v9 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
}

```

## disassembly

```asm
0x180056160  mov     [rsp-38h+arg_0], rbx
0x180056165  mov     [rsp-38h+arg_18], r9b
0x18005616a  mov     [rsp-38h+arg_10], r8
0x18005616f  push    rbp
0x180056170  push    rsi
0x180056171  push    rdi
0x180056172  push    r12
0x180056174  push    r13
0x180056176  push    r14
0x180056178  push    r15
0x18005617a  mov     rbp, rsp
0x18005617d  sub     rsp, 60h
0x180056181  cmp     cs:?s_fIsVisualTreeCallbackRegistered@Visual@Composition@UI@Windows@@0_NA, 0; bool Windows::UI::Composition::Visual::s_fIsVisualTreeCallbackRegistered
0x180056188  mov     r13, rdx
0x18005618b  mov     r14, rcx
0x18005618e  jnz     short loc_1800561A8
0x180056190  mov     rbx, [rsp+60h+arg_0]
0x180056198  add     rsp, 60h
0x18005619c  pop     r15
0x18005619e  pop     r14
0x1800561a0  pop     r13
0x1800561a2  pop     r12
0x1800561a4  pop     rdi
0x1800561a5  pop     rsi
0x1800561a6  pop     rbp
0x1800561a7  retn
0x1800561a8  xor     ebx, ebx
0x1800561aa  xor     edi, edi
0x1800561ac  xor     esi, esi
0x1800561ae  mov     [rbp+var_8], rbx
0x1800561b2  mov     [rbp+var_10], rdi
0x1800561b6  mov     [rbp+var_18], rsi
0x1800561ba  lea     r15d, [rbx+1]
0x1800561be  test    r14, r14
0x1800561c1  jz      loc_180056320
0x1800561c7  lea     rcx, [rbp+var_8]
0x1800561cb  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x1800561d0  lea     rbx, [r14+0B8h]
0x1800561d7  mov     eax, r15d
0x1800561da  mov     [rbp+var_8], rbx
0x1800561de  lock xadd [r14+10h], eax
0x1800561e4  add     eax, r15d
0x1800561e7  cmp     eax, r15d
0x1800561ea  jz      loc_180056330
0x1800561f0  mov     r12, rbx
0x1800561f3  test    r13, r13
0x1800561f6  jz      loc_180056328
0x1800561fc  lea     rcx, [rbp+var_10]
0x180056200  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x180056205  lea     rdi, [r13+0B8h]
0x18005620c  mov     eax, r15d
0x18005620f  mov     [rbp+var_10], rdi
0x180056213  lock xadd [r13+10h], eax
0x180056219  add     eax, r15d
0x18005621c  cmp     eax, r15d
0x18005621f  jz      loc_180056344
0x180056225  mov     r15, rdi
0x180056228  mov     r14, [rbp+arg_10]
0x18005622c  test    r14, r14
0x18005622f  jz      short loc_18005625E
0x180056231  lea     rcx, [rbp+var_18]
0x180056235  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005623a  lea     rsi, [r14+0B8h]
0x180056241  mov     eax, 1
0x180056246  mov     [rbp+var_18], rsi
0x18005624a  lock xadd [r14+10h], eax
0x180056250  inc     eax
0x180056252  cmp     eax, 1
0x180056255  jz      loc_180056359
0x18005625b  mov     r14, rsi
0x18005625e  xor     ecx, ecx; string
0x180056260  mov     [rbp+newString], 0
0x180056268  call    cs:__imp_WindowsDeleteString
0x18005626e  lea     rcx, [r13+80h]; this
0x180056275  mov     [rbp+newString], 0
0x18005627d  mov     edx, 1; unsigned int
0x180056282  call    ?GetReference@CSparseStorage@@QEBAPEAXI@Z; CSparseStorage::GetReference(uint)
0x180056287  lea     rdx, [rbp+newString]; newString
0x18005628b  mov     rcx, rax; string
0x18005628e  call    cs:__imp_WindowsDuplicateString
0x180056294  mov     rdx, [rbp+newString]
0x180056298  mov     r9, rsi
0x18005629b  mov     rcx, cs:qword_1801E0E40
0x1800562a2  mov     r8, rbx
0x1800562a5  mov     [rsp+60h+var_38], rdx
0x1800562aa  mov     dl, [rbp+arg_18]
0x1800562ad  mov     [rsp+60h+var_40], dl
0x1800562b1  mov     rdx, rdi
0x1800562b4  mov     rax, [rcx]
0x1800562b7  mov     rax, [rax+18h]
0x1800562bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800562c0  mov     rcx, [rbp+newString]; string
0x1800562c4  test    eax, eax
0x1800562c6  jns     loc_18005636D
0x1800562cc  call    cs:__imp_WindowsDeleteString
0x1800562d2  mov     [rbp+newString], 0
0x1800562da  test    r14, r14
0x1800562dd  jz      short loc_1800562EE
0x1800562df  mov     rax, [r14]
0x1800562e2  mov     rcx, r14
0x1800562e5  mov     rax, [rax+10h]
0x1800562e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800562ee  test    r15, r15
0x1800562f1  jz      short loc_180056302
0x1800562f3  mov     rax, [r15]
0x1800562f6  mov     rcx, r15
0x1800562f9  mov     rax, [rax+10h]
0x1800562fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056302  test    r12, r12
0x180056305  jz      loc_180056190
0x18005630b  mov     rax, [r12]
0x18005630f  mov     rcx, r12
0x180056312  mov     rax, [rax+10h]
0x180056316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005631b  jmp     loc_180056190
0x180056320  xor     r12d, r12d
0x180056323  jmp     loc_1800561F3
0x180056328  xor     r15d, r15d
0x18005632b  jmp     loc_180056228
0x180056330  mov     rax, [r14]
0x180056333  mov     rcx, r14
0x180056336  mov     rax, [rax+50h]
0x18005633a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005633f  jmp     loc_1800561F0
0x180056344  mov     rax, [r13+0]
0x180056348  mov     rcx, r13
0x18005634b  mov     rax, [rax+50h]
0x18005634f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056354  jmp     loc_180056225
0x180056359  mov     rax, [r14]
0x18005635c  mov     rcx, r14
0x18005635f  mov     rax, [rax+50h]
0x180056363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056368  jmp     loc_18005625B
0x18005636d  call    cs:__imp_WindowsDeleteString
0x180056373  lea     rcx, [rbp+var_18]
0x180056377  mov     [rbp+newString], 0
0x18005637f  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x180056384  lea     rcx, [rbp+var_10]
0x180056388  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005638d  lea     rcx, [rbp+var_8]
0x180056391  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x180056396  jmp     loc_180056190
```
