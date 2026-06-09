# CWMDSPPropImpl::~CWMDSPPropImpl(void)

- ea: `0x1800099bc`
- end: `0x180009a5f`
- name: `??1CWMDSPPropImpl@@QEAA@XZ`
- size: `163`
- prototype: `void __fastcall(CWMDSPPropImpl *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800098e8`

## callees

- `0x1800099bc`
- `0x180015104`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009a0f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009a0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a41`
- `OLEAUT32!__imp_SysFreeString` at `0x180009a4e`
- `OLEAUT32!__imp_SysFreeString` at `0x180009a4e`

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
        v7 = *(void **)(v5 + 72 * i + 16);
        if ( v7 )
          CoTaskMemFree(v7);
        *(_QWORD *)(v5 + 72 * i + 16) = 0;
      }
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v6 = (void *)*((_QWORD *)this + 3);
  if ( v6 )
    operator delete(v6);
}

```

## disassembly

```asm
0x1800099bc  push    rbx
0x1800099be  push    rbp
0x1800099bf  push    rsi
0x1800099c0  push    rdi
0x1800099c1  sub     rsp, 28h
0x1800099c5  cmp     qword ptr [rcx+18h], 0
0x1800099ca  lea     rax, ??_7CWMDSPPropImpl@@6B@; const CWMDSPPropImpl::`vftable'
0x1800099d1  mov     [rcx], rax
0x1800099d4  mov     rbx, rcx
0x1800099d7  jz      short loc_180009A0B
0x1800099d9  xor     edi, edi
0x1800099db  cmp     [rcx+8], edi
0x1800099de  jbe     short loc_180009A0B
0x1800099e0  mov     rax, [rbx+10h]
0x1800099e4  lea     rcx, [rdi+rdi*2]
0x1800099e8  mov     rbp, [rbx+18h]
0x1800099ec  lea     rsi, [rdi+rdi*8]
0x1800099f0  shl     rcx, 5
0x1800099f4  cmp     word ptr [rcx+rax+14h], 8
0x1800099fa  jz      short loc_180009A49
0x1800099fc  cmp     word ptr [rcx+rax+14h], 41h ; 'A'
0x180009a02  jz      short loc_180009A2C
0x180009a04  inc     edi
0x180009a06  cmp     edi, [rbx+8]
0x180009a09  jb      short loc_1800099E0
0x180009a0b  lea     rcx, [rbx+30h]; lpCriticalSection
0x180009a0f  call    cs:__imp_DeleteCriticalSection
0x180009a15  mov     rcx, [rbx+18h]; Block
0x180009a19  test    rcx, rcx
0x180009a1c  jz      short loc_180009A23
0x180009a1e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009a23  add     rsp, 28h
0x180009a27  pop     rdi
0x180009a28  pop     rsi
0x180009a29  pop     rbp
0x180009a2a  pop     rbx
0x180009a2b  retn
0x180009a2c  mov     rcx, [rbp+rsi*8+10h]; pv
0x180009a31  test    rcx, rcx
0x180009a34  jnz     short loc_180009A41
0x180009a36  mov     qword ptr [rbp+rsi*8+10h], 0
0x180009a3f  jmp     short loc_180009A04
0x180009a41  call    cs:__imp_CoTaskMemFree
0x180009a47  jmp     short loc_180009A36
0x180009a49  mov     rcx, [rbp+rsi*8+8]; bstrString
0x180009a4e  call    cs:__imp_SysFreeString
0x180009a54  mov     qword ptr [rbp+rsi*8+8], 0
0x180009a5d  jmp     short loc_180009A04
```
