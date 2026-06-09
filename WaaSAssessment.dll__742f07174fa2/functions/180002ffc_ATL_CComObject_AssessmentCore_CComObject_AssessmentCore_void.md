# ATL::CComObject<AssessmentCore>::~CComObject<AssessmentCore>(void)

- ea: `0x180002ffc`
- end: `0x18000307d`
- name: `??1?$CComObject@VAssessmentCore@@@ATL@@UEAA@XZ`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003240`

## callees

- `0x180002ffc`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003071`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003071`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003035`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003052`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003035`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003052`

## pseudocode

```c
void __fastcall ATL::CComObject<AssessmentCore>::~CComObject<AssessmentCore>(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<AssessmentCore>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v2 = *(void **)(a1 + 192);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *(_QWORD *)(a1 + 192) = 0;
  }
  v3 = *(void **)(a1 + 200);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *(_QWORD *)(a1 + 200) = 0;
  }
  if ( *(_BYTE *)(a1 + 56) )
  {
    *(_BYTE *)(a1 + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  }
}

```

## disassembly

```asm
0x180002ffc  push    rbx
0x180002ffe  sub     rsp, 20h
0x180003002  mov     dword ptr [rcx+8], 0C0000001h
0x180003009  lea     rax, ??_7?$CComObject@VAssessmentCore@@@ATL@@6B@; const ATL::CComObject<AssessmentCore>::`vftable'
0x180003010  mov     [rcx], rax
0x180003013  mov     rbx, rcx
0x180003016  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000301d  mov     rax, [rcx]
0x180003020  mov     rax, [rax+10h]
0x180003024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003029  mov     rcx, [rbx+0C0h]; pv
0x180003030  test    rcx, rcx
0x180003033  jz      short loc_180003046
0x180003035  call    cs:__imp_CoTaskMemFree
0x18000303b  mov     qword ptr [rbx+0C0h], 0
0x180003046  mov     rcx, [rbx+0C8h]; pv
0x18000304d  test    rcx, rcx
0x180003050  jz      short loc_180003063
0x180003052  call    cs:__imp_CoTaskMemFree
0x180003058  mov     qword ptr [rbx+0C8h], 0
0x180003063  lea     rcx, [rbx+10h]; lpCriticalSection
0x180003067  cmp     byte ptr [rcx+28h], 0
0x18000306b  jz      short loc_180003077
0x18000306d  mov     byte ptr [rcx+28h], 0
0x180003071  call    cs:__imp_DeleteCriticalSection
0x180003077  add     rsp, 20h
0x18000307b  pop     rbx
0x18000307c  retn
```
