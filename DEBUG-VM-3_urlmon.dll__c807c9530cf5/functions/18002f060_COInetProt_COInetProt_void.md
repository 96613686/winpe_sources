# COInetProt::~COInetProt(void)

- ea: `0x18002f060`
- end: `0x18002f20e`
- name: `??1COInetProt@@QEAA@XZ`
- size: `430`
- prototype: `void __fastcall(COInetProt *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002eae8`

## callees

- `0x18002f060`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f13d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f13d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f1e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f0e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f0fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f10c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f11e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f130`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f0e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f0fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f10c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f11e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f130`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f1f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f1f8`

## pseudocode

```c
void __fastcall COInetProt::~COInetProt(COInetProt *this)
{
  __int64 v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  __int64 v8; // rdi
  OLECHAR *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx

  *(_QWORD *)this = &COInetProt::`vftable'{for `IInternetProtocolEx'};
  *((_QWORD *)this + 1) = &COInetProt::`vftable'{for `IInternetProtocolSink'};
  *((_QWORD *)this + 2) = &COInetProt::`vftable'{for `IServiceProvider'};
  *((_QWORD *)this + 3) = &COInetProt::`vftable'{for `IInternetPriority'};
  *((_QWORD *)this + 4) = &COInetProt::`vftable'{for `IInternetPriorityInternal'};
  *((_QWORD *)this + 5) = &COInetProt::`vftable'{for `IUriContainer'};
  *((_QWORD *)this + 6) = &COInetProt::`vftable'{for `IBindingExInternal'};
  v2 = *((_QWORD *)this + 28);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 28) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 24);
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)this + 25);
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = (void *)*((_QWORD *)this + 26);
  if ( v5 )
    CoTaskMemFree(v5);
  v6 = (void *)*((_QWORD *)this + 27);
  if ( v6 )
    CoTaskMemFree(v6);
  v7 = (void *)*((_QWORD *)this + 19);
  if ( v7 )
    CoTaskMemFree(v7);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
  v8 = *((_QWORD *)this + 30);
  *((_QWORD *)this + 29) = &CUString::`vftable';
  if ( v8 || *((_DWORD *)this + 62) != 11 )
  {
    v9 = (OLECHAR *)*((_QWORD *)this + 32);
    if ( v9 )
    {
      SysFreeString(v9);
      *((_QWORD *)this + 32) = 0;
    }
    *((_QWORD *)this + 33) = 0;
    *((_DWORD *)this + 68) = 0;
    if ( v8 )
    {
      v10 = *((_QWORD *)this + 30);
      if ( v10 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        *((_QWORD *)this + 30) = 0;
      }
    }
  }
  *((_DWORD *)this + 62) = 11;
  v11 = *((_QWORD *)this + 15);
  if ( v11 )
  {
    *((_QWORD *)this + 15) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
}

```

## disassembly

```asm
0x18002f060  mov     [rsp+arg_0], rbx
0x18002f065  push    rdi
0x18002f066  sub     rsp, 20h
0x18002f06a  lea     rax, ??_7COInetProt@@6BIInternetProtocolEx@@@; const COInetProt::`vftable'{for `IInternetProtocolEx'}
0x18002f071  mov     rbx, rcx
0x18002f074  mov     [rcx], rax
0x18002f077  lea     rax, ??_7COInetProt@@6BIInternetProtocolSink@@@; const COInetProt::`vftable'{for `IInternetProtocolSink'}
0x18002f07e  mov     [rcx+8], rax
0x18002f082  lea     rax, ??_7COInetProt@@6BIServiceProvider@@@; const COInetProt::`vftable'{for `IServiceProvider'}
0x18002f089  mov     [rcx+10h], rax
0x18002f08d  lea     rax, ??_7COInetProt@@6BIInternetPriority@@@; const COInetProt::`vftable'{for `IInternetPriority'}
0x18002f094  mov     [rcx+18h], rax
0x18002f098  lea     rax, ??_7COInetProt@@6BIInternetPriorityInternal@@@; const COInetProt::`vftable'{for `IInternetPriorityInternal'}
0x18002f09f  mov     [rcx+20h], rax
0x18002f0a3  lea     rax, ??_7COInetProt@@6BIUriContainer@@@; const COInetProt::`vftable'{for `IUriContainer'}
0x18002f0aa  mov     [rcx+28h], rax
0x18002f0ae  lea     rax, ??_7COInetProt@@6BIBindingExInternal@@@; const COInetProt::`vftable'{for `IBindingExInternal'}
0x18002f0b5  mov     [rcx+30h], rax
0x18002f0b9  mov     rcx, [rcx+0E0h]
0x18002f0c0  test    rcx, rcx
0x18002f0c3  jz      short loc_18002F0DC
0x18002f0c5  mov     rax, [rcx]
0x18002f0c8  mov     rax, [rax+10h]
0x18002f0cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0d1  mov     qword ptr [rbx+0E0h], 0
0x18002f0dc  mov     rcx, [rbx+0C0h]; pv
0x18002f0e3  test    rcx, rcx
0x18002f0e6  jz      short loc_18002F0EE
0x18002f0e8  call    cs:__imp_CoTaskMemFree
0x18002f0ee  mov     rcx, [rbx+0C8h]; pv
0x18002f0f5  test    rcx, rcx
0x18002f0f8  jz      short loc_18002F100
0x18002f0fa  call    cs:__imp_CoTaskMemFree
0x18002f100  mov     rcx, [rbx+0D0h]; pv
0x18002f107  test    rcx, rcx
0x18002f10a  jz      short loc_18002F112
0x18002f10c  call    cs:__imp_CoTaskMemFree
0x18002f112  mov     rcx, [rbx+0D8h]; pv
0x18002f119  test    rcx, rcx
0x18002f11c  jz      short loc_18002F124
0x18002f11e  call    cs:__imp_CoTaskMemFree
0x18002f124  mov     rcx, [rbx+98h]; pv
0x18002f12b  test    rcx, rcx
0x18002f12e  jz      short loc_18002F136
0x18002f130  call    cs:__imp_CoTaskMemFree
0x18002f136  lea     rcx, [rbx+128h]; lpCriticalSection
0x18002f13d  call    cs:__imp_DeleteCriticalSection
0x18002f143  mov     rdi, [rbx+0F0h]
0x18002f14a  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x18002f151  mov     [rbx+0E8h], rax
0x18002f158  test    rdi, rdi
0x18002f15b  jz      loc_18002F1EA
0x18002f161  mov     rcx, [rbx+100h]; bstrString
0x18002f168  test    rcx, rcx
0x18002f16b  jnz     loc_18002F1F8
0x18002f171  mov     qword ptr [rbx+108h], 0
0x18002f17c  mov     dword ptr [rbx+110h], 0
0x18002f186  test    rdi, rdi
0x18002f189  jz      short loc_18002F1AE
0x18002f18b  mov     rcx, [rbx+0F0h]
0x18002f192  test    rcx, rcx
0x18002f195  jz      short loc_18002F1AE
0x18002f197  mov     rax, [rcx]
0x18002f19a  mov     rax, [rax+10h]
0x18002f19e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1a3  mov     qword ptr [rbx+0F0h], 0
0x18002f1ae  mov     dword ptr [rbx+0F8h], 0Bh
0x18002f1b8  mov     rcx, [rbx+78h]
0x18002f1bc  test    rcx, rcx
0x18002f1bf  jz      short loc_18002F1D5
0x18002f1c1  mov     qword ptr [rbx+78h], 0
0x18002f1c9  mov     rax, [rcx]
0x18002f1cc  mov     rax, [rax+10h]
0x18002f1d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1d5  lea     rcx, [rbx+40h]
0x18002f1d9  mov     rbx, [rsp+28h+arg_0]
0x18002f1de  add     rsp, 20h
0x18002f1e2  pop     rdi
0x18002f1e3  jmp     cs:__imp_DeleteCriticalSection
0x18002f1ea  cmp     dword ptr [rbx+0F8h], 0Bh
0x18002f1f1  jz      short loc_18002F1AE
0x18002f1f3  jmp     loc_18002F161
0x18002f1f8  call    cs:__imp_SysFreeString
0x18002f1fe  mov     qword ptr [rbx+100h], 0
0x18002f209  jmp     loc_18002F171
```
