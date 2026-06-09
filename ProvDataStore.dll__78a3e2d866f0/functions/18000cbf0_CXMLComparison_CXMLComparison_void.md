# CXMLComparison::~CXMLComparison(void)

- ea: `0x18000cbf0`
- end: `0x18000ccd4`
- name: `??1CXMLComparison@@UEAA@XZ`
- size: `228`
- prototype: `void __fastcall(CXMLComparison *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000cd10`

## callees

- `0x18000cbf0`
- `0x180012010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000cc7a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cca2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cc7a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc5a`

## pseudocode

```c
void __fastcall CXMLComparison::~CXMLComparison(CXMLComparison *this)
{
  __int64 v2; // rcx
  __int64 i; // rsi
  __int64 v4; // rcx

  *(_QWORD *)this = &CXMLComparison::`vftable';
  v2 = *((_QWORD *)this + 1);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( *((_QWORD *)this + 12) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 26); i = (unsigned int)(i + 1) )
    {
      v4 = *(_QWORD *)(*((_QWORD *)this + 12) + 8 * i);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      *(_QWORD *)(*((_QWORD *)this + 12) + 8 * i) = 0;
    }
    CoTaskMemFree(*((LPVOID *)this + 12));
    *((_QWORD *)this + 12) = 0;
    *((_DWORD *)this + 26) = 0;
  }
  if ( *((_QWORD *)this + 9) >= 8u )
    operator delete(*((void **)this + 6));
  *((_QWORD *)this + 9) = 7;
  *((_QWORD *)this + 8) = 0;
  *((_WORD *)this + 24) = 0;
  if ( *((_QWORD *)this + 5) >= 8u )
    operator delete(*((void **)this + 2));
  *((_QWORD *)this + 5) = 7;
  *((_QWORD *)this + 4) = 0;
  *((_WORD *)this + 8) = 0;
  *(_QWORD *)this = &IMVXMLComparison::`vftable';
}

```

## disassembly

```asm
0x18000cbf0  mov     [rsp+arg_0], rbx
0x18000cbf5  mov     [rsp+arg_8], rsi
0x18000cbfa  push    rdi
0x18000cbfb  sub     rsp, 20h
0x18000cbff  mov     rdi, rcx
0x18000cc02  lea     rax, ??_7CXMLComparison@@6B@; const CXMLComparison::`vftable'
0x18000cc09  mov     [rcx], rax
0x18000cc0c  mov     rcx, [rcx+8]
0x18000cc10  test    rcx, rcx
0x18000cc13  jz      short loc_18000CC21
0x18000cc15  mov     rax, [rcx]
0x18000cc18  mov     rax, [rax+10h]
0x18000cc1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc21  cmp     qword ptr [rdi+60h], 0
0x18000cc26  jz      short loc_18000CC6F
0x18000cc28  xor     esi, esi
0x18000cc2a  cmp     [rdi+68h], esi
0x18000cc2d  jbe     short loc_18000CC56
0x18000cc2f  mov     rax, [rdi+60h]
0x18000cc33  mov     rcx, [rax+rsi*8]
0x18000cc37  mov     rax, [rcx]
0x18000cc3a  mov     rax, [rax+10h]
0x18000cc3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc43  mov     rax, [rdi+60h]
0x18000cc47  mov     qword ptr [rax+rsi*8], 0
0x18000cc4f  inc     esi
0x18000cc51  cmp     esi, [rdi+68h]
0x18000cc54  jb      short loc_18000CC2F
0x18000cc56  mov     rcx, [rdi+60h]; pv
0x18000cc5a  call    cs:__imp_CoTaskMemFree
0x18000cc60  mov     qword ptr [rdi+60h], 0
0x18000cc68  mov     dword ptr [rdi+68h], 0
0x18000cc6f  cmp     qword ptr [rdi+48h], 8
0x18000cc74  jb      short loc_18000CC80
0x18000cc76  mov     rcx, [rdi+30h]
0x18000cc7a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cc80  mov     ebx, 7
0x18000cc85  mov     [rdi+48h], rbx
0x18000cc89  mov     qword ptr [rdi+40h], 0
0x18000cc91  xor     eax, eax
0x18000cc93  mov     [rdi+30h], ax
0x18000cc97  cmp     qword ptr [rdi+28h], 8
0x18000cc9c  jb      short loc_18000CCA8
0x18000cc9e  mov     rcx, [rdi+10h]
0x18000cca2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cca8  mov     [rdi+28h], rbx
0x18000ccac  mov     qword ptr [rdi+20h], 0
0x18000ccb4  xor     eax, eax
0x18000ccb6  mov     [rdi+10h], ax
0x18000ccba  lea     rax, ??_7IMVXMLComparison@@6B@; const IMVXMLComparison::`vftable'
0x18000ccc1  mov     [rdi], rax
0x18000ccc4  mov     rbx, [rsp+28h+arg_0]
0x18000ccc9  mov     rsi, [rsp+28h+arg_8]
0x18000ccce  add     rsp, 20h
0x18000ccd2  pop     rdi
0x18000ccd3  retn
```
