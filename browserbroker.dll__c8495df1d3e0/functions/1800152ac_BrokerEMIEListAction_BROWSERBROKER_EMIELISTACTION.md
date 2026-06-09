# BrokerEMIEListAction(_BROWSERBROKER_EMIELISTACTION)

- ea: `0x1800152ac`
- end: `0x180015347`
- name: `?BrokerEMIEListAction@@YAJW4_BROWSERBROKER_EMIELISTACTION@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008890`

## callees

- `0x180006cc4`
- `0x1800152ac`
- `0x180015350`
- `0x18002d010`

## import_xrefs

- `urlmon!__imp_CreateDomainListBrowserEmulationFilter` at `0x1800152d9`
- `urlmon!__imp_CreateDomainListBrowserEmulationFilter` at `0x18001530d`
- `urlmon!__imp_CreateDomainListBrowserEmulationFilter` at `0x1800152d9`
- `urlmon!__imp_CreateDomainListBrowserEmulationFilter` at `0x18001530d`

## pseudocode

```c
__int64 __fastcall BrokerEMIEListAction(int a1)
{
  unsigned int v1; // ebx
  int v2; // ecx
  int v3; // ecx
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  v1 = -2147418113;
  v2 = a1 - 1;
  if ( !v2 )
    return (unsigned int)UpdateEMIEList();
  v3 = v2 - 1;
  if ( !v3 )
  {
    v5 = 0;
    v1 = CreateDomainListBrowserEmulationFilter(5, &v5);
    if ( !v1 )
      v1 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 80LL))(v5);
    goto LABEL_9;
  }
  if ( v3 == 1 )
  {
    v5 = 0;
    v1 = CreateDomainListBrowserEmulationFilter(5, &v5);
    if ( !v1 )
      v1 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 88LL))(v5);
LABEL_9:
    ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(&v5);
  }
  return v1;
}

```

## disassembly

```asm
0x1800152ac  push    rbx
0x1800152ae  sub     rsp, 20h
0x1800152b2  mov     ebx, 8000FFFFh
0x1800152b7  sub     ecx, 1
0x1800152ba  jz      short loc_180015338
0x1800152bc  sub     ecx, 1
0x1800152bf  jz      short loc_1800152FA
0x1800152c1  cmp     ecx, 1
0x1800152c4  jnz     short loc_18001533F
0x1800152c6  mov     [rsp+28h+arg_8], 0
0x1800152cf  lea     rdx, [rsp+28h+arg_8]
0x1800152d4  mov     ecx, 5
0x1800152d9  call    cs:__imp_CreateDomainListBrowserEmulationFilter
0x1800152df  mov     ebx, eax
0x1800152e1  test    eax, eax
0x1800152e3  jnz     short loc_1800152F8
0x1800152e5  mov     rcx, [rsp+28h+arg_8]
0x1800152ea  mov     rax, [rcx]
0x1800152ed  mov     rax, [rax+58h]
0x1800152f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152f6  mov     ebx, eax
0x1800152f8  jmp     short loc_18001532C
0x1800152fa  mov     [rsp+28h+arg_8], 0
0x180015303  lea     rdx, [rsp+28h+arg_8]
0x180015308  mov     ecx, 5
0x18001530d  call    cs:__imp_CreateDomainListBrowserEmulationFilter
0x180015313  mov     ebx, eax
0x180015315  test    eax, eax
0x180015317  jnz     short loc_18001532C
0x180015319  mov     rcx, [rsp+28h+arg_8]
0x18001531e  mov     rax, [rcx]
0x180015321  mov     rax, [rax+50h]
0x180015325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001532a  mov     ebx, eax
0x18001532c  lea     rcx, [rsp+28h+arg_8]
0x180015331  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x180015336  jmp     short loc_18001533F
0x180015338  call    UpdateEMIEList
0x18001533d  mov     ebx, eax
0x18001533f  mov     eax, ebx
0x180015341  add     rsp, 20h
0x180015345  pop     rbx
0x180015346  retn
```
