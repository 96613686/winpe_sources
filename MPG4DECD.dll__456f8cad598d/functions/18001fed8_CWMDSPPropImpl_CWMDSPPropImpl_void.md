# CWMDSPPropImpl::~CWMDSPPropImpl(void)

- ea: `0x18001fed8`
- end: `0x18001ff77`
- name: `??1CWMDSPPropImpl@@QEAA@XZ`
- size: `159`
- prototype: `void __fastcall(CWMDSPPropImpl *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180002858`

## callees

- `0x1800014a8`
- `0x18001fed8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ff5a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ff5a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ff40`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ff40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff2a`

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
0x18001fed8  push    rbx
0x18001feda  push    rbp
0x18001fedb  push    rsi
0x18001fedc  push    rdi
0x18001fedd  sub     rsp, 28h
0x18001fee1  cmp     qword ptr [rcx+18h], 0
0x18001fee6  lea     rax, ??_7CWMDSPPropImpl@@6B@; const CWMDSPPropImpl::`vftable'
0x18001feed  mov     [rcx], rax
0x18001fef0  mov     rbx, rcx
0x18001fef3  jz      short loc_18001FF56
0x18001fef5  xor     edi, edi
0x18001fef7  cmp     [rcx+8], edi
0x18001fefa  jbe     short loc_18001FF56
0x18001fefc  mov     rax, [rbx+10h]
0x18001ff00  lea     rcx, [rdi+rdi*2]
0x18001ff04  mov     rbp, [rbx+18h]
0x18001ff08  lea     rsi, [rdi+rdi*8]
0x18001ff0c  shl     rcx, 5
0x18001ff10  cmp     word ptr [rcx+rax+14h], 8
0x18001ff16  jz      short loc_18001FF3B
0x18001ff18  cmp     word ptr [rcx+rax+14h], 41h ; 'A'
0x18001ff1e  jnz     short loc_18001FF4F
0x18001ff20  mov     rcx, [rbp+rsi*8+10h]; pv
0x18001ff25  test    rcx, rcx
0x18001ff28  jz      short loc_18001FF30
0x18001ff2a  call    cs:__imp_CoTaskMemFree
0x18001ff30  mov     qword ptr [rbp+rsi*8+10h], 0
0x18001ff39  jmp     short loc_18001FF4F
0x18001ff3b  mov     rcx, [rbp+rsi*8+8]; bstrString
0x18001ff40  call    cs:__imp_SysFreeString
0x18001ff46  mov     qword ptr [rbp+rsi*8+8], 0
0x18001ff4f  inc     edi
0x18001ff51  cmp     edi, [rbx+8]
0x18001ff54  jb      short loc_18001FEFC
0x18001ff56  lea     rcx, [rbx+30h]; lpCriticalSection
0x18001ff5a  call    cs:__imp_DeleteCriticalSection
0x18001ff60  mov     rcx, [rbx+18h]; Block
0x18001ff64  test    rcx, rcx
0x18001ff67  jz      short loc_18001FF6E
0x18001ff69  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ff6e  add     rsp, 28h
0x18001ff72  pop     rdi
0x18001ff73  pop     rsi
0x18001ff74  pop     rbp
0x18001ff75  pop     rbx
0x18001ff76  retn
```
