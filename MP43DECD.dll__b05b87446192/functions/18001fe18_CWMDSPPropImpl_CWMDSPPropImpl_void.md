# CWMDSPPropImpl::~CWMDSPPropImpl(void)

- ea: `0x18001fe18`
- end: `0x18001feb7`
- name: `??1CWMDSPPropImpl@@QEAA@XZ`
- size: `159`
- prototype: `void __fastcall(CWMDSPPropImpl *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000279c`

## callees

- `0x180001478`
- `0x18001fe18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fe9a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fe9a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fe80`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fe80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fe6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fe6a`

## pseudocode

```c
void __fastcall CWMDSPPropImpl::~CWMDSPPropImpl(CWMDSPPropImpl *this)
{
  bool v1; // zf
  __int64 i; // rdi
  __int64 v4; // rax
  __int64 v5; // rbp
  void *v6; // rcx
  void *v7; // rcx

  v1 = *((_QWORD *)this + 3) == 0;
  *(_QWORD *)this = &CWMDSPPropImpl::`vftable';
  if ( !v1 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 2); i = (unsigned int)(i + 1) )
    {
      v4 = *((_QWORD *)this + 2);
      v5 = *((_QWORD *)this + 3);
      if ( *(_WORD *)(96 * i + v4 + 20) == 8 )
      {
        SysFreeString(*(BSTR *)(v5 + 72 * i + 8));
        *(_QWORD *)(v5 + 72 * i + 8) = 0;
      }
      else if ( *(_WORD *)(96 * i + v4 + 20) == 65 )
      {
        v6 = *(void **)(v5 + 72 * i + 16);
        if ( v6 )
          CoTaskMemFree(v6);
        *(_QWORD *)(v5 + 72 * i + 16) = 0;
      }
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v7 = (void *)*((_QWORD *)this + 3);
  if ( v7 )
    operator delete(v7);
}

```

## disassembly

```asm
0x18001fe18  push    rbx
0x18001fe1a  push    rbp
0x18001fe1b  push    rsi
0x18001fe1c  push    rdi
0x18001fe1d  sub     rsp, 28h
0x18001fe21  cmp     qword ptr [rcx+18h], 0
0x18001fe26  lea     rax, ??_7CWMDSPPropImpl@@6B@; const CWMDSPPropImpl::`vftable'
0x18001fe2d  mov     [rcx], rax
0x18001fe30  mov     rbx, rcx
0x18001fe33  jz      short loc_18001FE96
0x18001fe35  xor     edi, edi
0x18001fe37  cmp     [rcx+8], edi
0x18001fe3a  jbe     short loc_18001FE96
0x18001fe3c  mov     rax, [rbx+10h]
0x18001fe40  lea     rcx, [rdi+rdi*2]
0x18001fe44  mov     rbp, [rbx+18h]
0x18001fe48  lea     rsi, [rdi+rdi*8]
0x18001fe4c  shl     rcx, 5
0x18001fe50  cmp     word ptr [rcx+rax+14h], 8
0x18001fe56  jz      short loc_18001FE7B
0x18001fe58  cmp     word ptr [rcx+rax+14h], 41h ; 'A'
0x18001fe5e  jnz     short loc_18001FE8F
0x18001fe60  mov     rcx, [rbp+rsi*8+10h]; pv
0x18001fe65  test    rcx, rcx
0x18001fe68  jz      short loc_18001FE70
0x18001fe6a  call    cs:__imp_CoTaskMemFree
0x18001fe70  mov     qword ptr [rbp+rsi*8+10h], 0
0x18001fe79  jmp     short loc_18001FE8F
0x18001fe7b  mov     rcx, [rbp+rsi*8+8]; bstrString
0x18001fe80  call    cs:__imp_SysFreeString
0x18001fe86  mov     qword ptr [rbp+rsi*8+8], 0
0x18001fe8f  inc     edi
0x18001fe91  cmp     edi, [rbx+8]
0x18001fe94  jb      short loc_18001FE3C
0x18001fe96  lea     rcx, [rbx+30h]; lpCriticalSection
0x18001fe9a  call    cs:__imp_DeleteCriticalSection
0x18001fea0  mov     rcx, [rbx+18h]; Block
0x18001fea4  test    rcx, rcx
0x18001fea7  jz      short loc_18001FEAE
0x18001fea9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001feae  add     rsp, 28h
0x18001feb2  pop     rdi
0x18001feb3  pop     rsi
0x18001feb4  pop     rbp
0x18001feb5  pop     rbx
0x18001feb6  retn
```
