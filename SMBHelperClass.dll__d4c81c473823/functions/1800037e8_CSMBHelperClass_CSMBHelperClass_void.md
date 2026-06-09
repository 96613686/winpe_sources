# CSMBHelperClass::~CSMBHelperClass(void)

- ea: `0x1800037e8`
- end: `0x1800039ab`
- name: `??1CSMBHelperClass@@QEAA@XZ`
- size: `451`
- prototype: `void __fastcall(CSMBHelperClass *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180003af0`

## callees

- `0x1800037e8`
- `0x180005050`
- `0x18000cbac`
- `0x18000d4d8`
- `0x18000f3f8`
- `0x180012010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000386b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003892`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800038b9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800038e3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000386b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003892`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800038b9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800038e3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003932`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003932`
- `KERNEL32!WaitForSingleObject` at `0x180003806`
- `KERNEL32!WaitForSingleObject` at `0x180003806`
- `KERNEL32!CloseHandle` at `0x180003810`
- `KERNEL32!CloseHandle` at `0x180003810`
- `KERNEL32!DeleteCriticalSection` at `0x180003994`
- `KERNEL32!DeleteCriticalSection` at `0x180003994`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003836`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003836`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSMBHelperClass::~CSMBHelperClass(CSMBHelperClass *this)
{
  void *v2; // rcx
  LPVOID *i; // rbx
  _QWORD *v4; // rcx
  __int64 v5; // rsi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  void *v11; // rcx

  v2 = (void *)*((_QWORD *)this + 15);
  if ( v2 )
  {
    WaitForSingleObject(v2, 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 15));
    *((_QWORD *)this + 15) = 0;
  }
  for ( i = (LPVOID *)*((_QWORD *)this + 31); i != *((LPVOID **)this + 32); ++i )
  {
    if ( *i )
      CoTaskMemFree(*i);
  }
  v4 = (_QWORD *)*((_QWORD *)this + 16);
  if ( v4 )
  {
    v5 = 0;
    while ( (unsigned int)v5 < 0xF )
    {
      v6 = (void *)v4[5 * v5 + 1];
      if ( v6 )
      {
        operator delete[](v6);
        *(_QWORD *)(*((_QWORD *)this + 16) + 40 * v5 + 8) = 0;
      }
      v7 = *(void **)(*((_QWORD *)this + 16) + 40 * v5 + 16);
      if ( v7 )
      {
        operator delete[](v7);
        *(_QWORD *)(*((_QWORD *)this + 16) + 40 * v5 + 16) = 0;
      }
      v8 = *(void **)(*((_QWORD *)this + 16) + 40 * v5 + 24);
      if ( v8 )
      {
        operator delete[](v8);
        *(_QWORD *)(*((_QWORD *)this + 16) + 40 * v5 + 24) = 0;
      }
      v5 = (unsigned int)(v5 + 1);
      v4 = (_QWORD *)*((_QWORD *)this + 16);
      if ( !v4 )
        goto LABEL_20;
    }
    operator delete[](v4);
    *((_QWORD *)this + 16) = 0;
  }
LABEL_20:
  v9 = *((_QWORD *)this + 22);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  v10 = *((_QWORD *)this + 37);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v11 = (void *)*((_QWORD *)this + 31);
  if ( v11 )
  {
    operator delete(v11);
    *((_QWORD *)this + 31) = 0;
    *((_QWORD *)this + 32) = 0;
    *((_QWORD *)this + 33) = 0;
  }
  RequiredAttributeList::~RequiredAttributeList((CSMBHelperClass *)((char *)this + 232));
  AttributeList::~AttributeList((CSMBHelperClass *)((char *)this + 208));
  RootCauseList::~RootCauseList((CSMBHelperClass *)((char *)this + 184));
  _attributes_array_t::FreeAll((CSMBHelperClass *)((char *)this + 24));
  if ( *((_BYTE *)this + 112) )
  {
    *((_BYTE *)this + 112) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  }
}

```

## disassembly

```asm
0x1800037e8  mov     [rsp+arg_0], rbx
0x1800037ed  mov     [rsp+arg_8], rsi
0x1800037f2  push    rdi
0x1800037f3  sub     rsp, 20h
0x1800037f7  mov     rdi, rcx
0x1800037fa  mov     rcx, [rcx+78h]; hHandle
0x1800037fe  test    rcx, rcx
0x180003801  jz      short loc_18000381E
0x180003803  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003806  call    cs:__imp_WaitForSingleObject
0x18000380c  mov     rcx, [rdi+78h]; hObject
0x180003810  call    cs:__imp_CloseHandle
0x180003816  mov     qword ptr [rdi+78h], 0
0x18000381e  mov     rbx, [rdi+0F8h]
0x180003825  cmp     rbx, [rdi+100h]
0x18000382c  jz      short loc_180003842
0x18000382e  mov     rcx, [rbx]; pv
0x180003831  test    rcx, rcx
0x180003834  jz      short loc_18000383C
0x180003836  call    cs:__imp_CoTaskMemFree
0x18000383c  add     rbx, 8
0x180003840  jmp     short loc_180003825
0x180003842  mov     rcx, [rdi+80h]
0x180003849  test    rcx, rcx
0x18000384c  jz      loc_1800038F4
0x180003852  xor     esi, esi
0x180003854  cmp     esi, 0Fh
0x180003857  jnb     loc_1800038E3
0x18000385d  lea     rbx, [rsi+rsi*4]
0x180003861  mov     rcx, [rcx+rbx*8+8]
0x180003866  test    rcx, rcx
0x180003869  jz      short loc_180003881
0x18000386b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003871  mov     rax, [rdi+80h]
0x180003878  mov     qword ptr [rax+rbx*8+8], 0
0x180003881  mov     rax, [rdi+80h]
0x180003888  mov     rcx, [rax+rbx*8+10h]
0x18000388d  test    rcx, rcx
0x180003890  jz      short loc_1800038A8
0x180003892  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003898  mov     rax, [rdi+80h]
0x18000389f  mov     qword ptr [rax+rbx*8+10h], 0
0x1800038a8  mov     rax, [rdi+80h]
0x1800038af  mov     rcx, [rax+rbx*8+18h]
0x1800038b4  test    rcx, rcx
0x1800038b7  jz      short loc_1800038CF
0x1800038b9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800038bf  mov     rax, [rdi+80h]
0x1800038c6  mov     qword ptr [rax+rbx*8+18h], 0
0x1800038cf  inc     esi
0x1800038d1  mov     rcx, [rdi+80h]
0x1800038d8  test    rcx, rcx
0x1800038db  jnz     loc_180003854
0x1800038e1  jmp     short loc_1800038F4
0x1800038e3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800038e9  mov     qword ptr [rdi+80h], 0
0x1800038f4  mov     rcx, [rdi+0B0h]
0x1800038fb  test    rcx, rcx
0x1800038fe  jz      short loc_18000390D
0x180003900  mov     rax, [rcx]
0x180003903  mov     rax, [rax+10h]
0x180003907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000390c  nop
0x18000390d  mov     rcx, [rdi+128h]
0x180003914  test    rcx, rcx
0x180003917  jz      short loc_180003926
0x180003919  mov     rax, [rcx]
0x18000391c  mov     rax, [rax+10h]
0x180003920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003925  nop
0x180003926  mov     rcx, [rdi+0F8h]
0x18000392d  test    rcx, rcx
0x180003930  jz      short loc_180003959
0x180003932  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003938  mov     qword ptr [rdi+0F8h], 0
0x180003943  mov     qword ptr [rdi+100h], 0
0x18000394e  mov     qword ptr [rdi+108h], 0
0x180003959  lea     rcx, [rdi+0E8h]; this
0x180003960  call    ??1RequiredAttributeList@@QEAA@XZ; RequiredAttributeList::~RequiredAttributeList(void)
0x180003965  lea     rcx, [rdi+0D0h]; this
0x18000396c  call    ??1AttributeList@@QEAA@XZ; AttributeList::~AttributeList(void)
0x180003971  lea     rcx, [rdi+0B8h]; this
0x180003978  call    ??1RootCauseList@@QEAA@XZ; RootCauseList::~RootCauseList(void)
0x18000397d  lea     rcx, [rdi+18h]; this
0x180003981  call    ?FreeAll@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeAll(void)
0x180003986  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000398a  cmp     byte ptr [rcx+28h], 0
0x18000398e  jz      short loc_18000399B
0x180003990  mov     byte ptr [rcx+28h], 0
0x180003994  call    cs:__imp_DeleteCriticalSection
0x18000399a  nop
0x18000399b  mov     rbx, [rsp+28h+arg_0]
0x1800039a0  mov     rsi, [rsp+28h+arg_8]
0x1800039a5  add     rsp, 20h
0x1800039a9  pop     rdi
0x1800039aa  retn
```
