# CNetDiagHelperImpl::Initialize(ulong,tagHELPER_ATTRIBUTE * const)

- ea: `0x1800043a0`
- end: `0x1800044eb`
- name: `?Initialize@CNetDiagHelperImpl@@UEAAJKQEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `331`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *this, unsigned int, struct tagHELPER_ATTRIBUTE *const)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180003b60`
- `0x1800043a0`
- `0x180006ebc`
- `0x18000c168`
- `0x18000c57e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004498`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004498`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::Initialize(
        CNetDiagHelperImpl *this,
        unsigned int a2,
        struct tagHELPER_ATTRIBUTE *const a3)
{
  LPVOID *v6; // r15
  __int64 result; // rax
  const struct tagHelperAttributeInfo near *const *v8; // rdi
  int v9; // r12d
  int v10; // ebp
  _QWORD *v11; // r14
  unsigned int v12; // esi
  __int64 i; // rbx
  __int64 v14; // rax
  bool v15; // zf
  __int64 v16; // rcx

  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 1, 0) )
    MicrosoftTelemetryAssertTriggeredNoArgs(1);
  v6 = (LPVOID *)((char *)this + 24);
  if ( !a2 && !*(_DWORD *)v6 && !*((_QWORD *)this + 4) )
    return 0;
  result = _attributes_array_t::Copy((LPVOID *)this + 3, a2, a3);
  if ( (int)result >= 0 )
  {
    v8 = &CNetDiagHelperImpl::m_attrInfos;
    v9 = 0;
    if ( !a2 )
      return 0;
LABEL_9:
    if ( v8 && (v10 = *((_DWORD *)v8 + 2)) != 0 )
    {
      v11 = v6[1];
      if ( v11 )
      {
        v12 = *(_DWORD *)v6;
        for ( i = 0; (unsigned int)i < v12; i = (unsigned int)(i + 1) )
        {
          if ( LODWORD(v11[18 * i + 1]) == v10 )
          {
            v14 = v11[18 * i];
            if ( *v8 )
            {
              if ( !v14 )
                continue;
              v15 = wcsncmp_0((const wchar_t *)v11[18 * i], *(const wchar_t **)v8, 0xFFu) == 0;
            }
            else
            {
              v15 = v14 == 0;
            }
            if ( v15 )
            {
              if ( ++v9 < a2 )
              {
                v8 += 2;
                goto LABEL_9;
              }
              return 0;
            }
          }
        }
      }
      _attributes_array_t::FreeElements((_attributes_array_t *)v6);
      CoTaskMemFree(v6[1]);
      v6[1] = 0;
      *(_DWORD *)v6 = 0;
      MicrosoftTelemetryAssertTriggeredNoArgs(v16);
      return 2147942487LL;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800043a0  push    rbx
0x1800043a2  push    rdi
0x1800043a3  push    r13
0x1800043a5  push    r15
0x1800043a7  sub     rsp, 28h
0x1800043ab  mov     rbx, rcx
0x1800043ae  mov     rdi, r8
0x1800043b1  mov     ecx, 1
0x1800043b6  mov     r13d, edx
0x1800043b9  xor     eax, eax
0x1800043bb  lock cmpxchg [rbx+10h], ecx
0x1800043c0  jz      short loc_1800043C7
0x1800043c2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800043c7  lea     r15, [rbx+18h]
0x1800043cb  test    r13d, r13d
0x1800043ce  jnz     short loc_1800043E9
0x1800043d0  cmp     [r15], r13d
0x1800043d3  jnz     short loc_1800043E9
0x1800043d5  cmp     qword ptr [r15+8], 0
0x1800043da  jnz     short loc_1800043E9
0x1800043dc  xor     eax, eax
0x1800043de  add     rsp, 28h
0x1800043e2  pop     r15
0x1800043e4  pop     r13
0x1800043e6  pop     rdi
0x1800043e7  pop     rbx
0x1800043e8  retn
0x1800043e9  mov     r8, rdi; struct tagHELPER_ATTRIBUTE *
0x1800043ec  mov     edx, r13d; unsigned int
0x1800043ef  mov     rcx, r15; this
0x1800043f2  call    ?Copy@_attributes_array_t@@QEAAJKPEAUtagHELPER_ATTRIBUTE@@@Z; _attributes_array_t::Copy(ulong,tagHELPER_ATTRIBUTE *)
0x1800043f7  test    eax, eax
0x1800043f9  js      loc_1800044E0
0x1800043ff  mov     [rsp+48h+arg_0], rbp
0x180004404  lea     rdi, ?m_attrInfos@CNetDiagHelperImpl@@0QBUtagHelperAttributeInfo@@B; tagHelperAttributeInfo const near * const CNetDiagHelperImpl::m_attrInfos
0x18000440b  mov     [rsp+48h+arg_8], rsi
0x180004410  mov     [rsp+48h+arg_10], r12
0x180004415  xor     r12d, r12d
0x180004418  mov     [rsp+48h+var_28], r14
0x18000441d  test    r13d, r13d
0x180004420  jz      loc_1800044CA
0x180004426  test    rdi, rdi
0x180004429  jz      loc_1800044CA
0x18000442f  mov     ebp, [rdi+8]
0x180004432  test    ebp, ebp
0x180004434  jz      loc_1800044CA
0x18000443a  mov     r14, [r15+8]
0x18000443e  test    r14, r14
0x180004441  jz      short loc_18000448C
0x180004443  mov     esi, [r15]
0x180004446  xor     ebx, ebx
0x180004448  test    esi, esi
0x18000444a  jz      short loc_18000448C
0x18000444c  nop     dword ptr [rax+00h]
0x180004450  lea     rcx, [rbx+rbx*8]
0x180004454  add     rcx, rcx
0x180004457  cmp     [r14+rcx*8+8], ebp
0x18000445c  jnz     short loc_180004486
0x18000445e  mov     rdx, [rdi]; String2
0x180004461  mov     rax, [r14+rcx*8]
0x180004465  test    rdx, rdx
0x180004468  jz      short loc_180004481
0x18000446a  test    rax, rax
0x18000446d  jz      short loc_180004486
0x18000446f  mov     r8d, 0FFh; MaxCount
0x180004475  mov     rcx, rax; String1
0x180004478  call    wcsncmp_0
0x18000447d  test    eax, eax
0x18000447f  jmp     short loc_180004484
0x180004481  test    rax, rax
0x180004484  jz      short loc_1800044B9
0x180004486  inc     ebx
0x180004488  cmp     ebx, esi
0x18000448a  jb      short loc_180004450
0x18000448c  mov     rcx, r15; this
0x18000448f  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x180004494  mov     rcx, [r15+8]; pv
0x180004498  call    cs:__imp_CoTaskMemFree
0x18000449e  mov     qword ptr [r15+8], 0
0x1800044a6  mov     dword ptr [r15], 0
0x1800044ad  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800044b2  mov     eax, 80070057h
0x1800044b7  jmp     short loc_1800044CC
0x1800044b9  inc     r12d
0x1800044bc  cmp     r12d, r13d
0x1800044bf  jnb     short loc_1800044CA
0x1800044c1  add     rdi, 10h
0x1800044c5  jmp     loc_180004426
0x1800044ca  xor     eax, eax
0x1800044cc  mov     r12, [rsp+48h+arg_10]
0x1800044d1  mov     rsi, [rsp+48h+arg_8]
0x1800044d6  mov     rbp, [rsp+48h+arg_0]
0x1800044db  mov     r14, [rsp+48h+var_28]
0x1800044e0  add     rsp, 28h
0x1800044e4  pop     r15
0x1800044e6  pop     r13
0x1800044e8  pop     rdi
0x1800044e9  pop     rbx
0x1800044ea  retn
```
