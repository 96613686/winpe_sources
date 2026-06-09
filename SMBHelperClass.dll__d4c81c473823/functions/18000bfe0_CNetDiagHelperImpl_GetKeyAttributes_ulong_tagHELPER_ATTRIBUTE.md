# CNetDiagHelperImpl::GetKeyAttributes(ulong *,tagHELPER_ATTRIBUTE * *)

- ea: `0x18000bfe0`
- end: `0x18000c0f4`
- name: `?GetKeyAttributes@CNetDiagHelperImpl@@UEAAJPEAKPEAPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, unsigned int *, struct tagHELPER_ATTRIBUTE **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180005050`
- `0x18000b8ac`
- `0x18000bfe0`
- `0x18000fa98`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c061`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c061`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::GetKeyAttributes(
        CNetDiagHelperImpl *this,
        unsigned int *a2,
        struct tagHELPER_ATTRIBUTE **a3)
{
  __int64 v6; // r15
  unsigned int v7; // ebx
  __int64 v8; // rbx
  struct tagHELPER_ATTRIBUTE *v9; // rax
  struct tagHELPER_ATTRIBUTE *v10; // rbp
  __int64 i; // rbx
  int v13; // [rsp+20h] [rbp-48h] BYREF
  struct tagHELPER_ATTRIBUTE *v14; // [rsp+28h] [rbp-40h]

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  v6 = *((unsigned int *)this + 6);
  v13 = 0;
  v14 = 0;
  if ( (unsigned int)v6 > 0x1C71C71 )
  {
    v7 = -2147024362;
LABEL_13:
    _attributes_array_t::FreeAll((_attributes_array_t *)&v13);
    return v7;
  }
  _attributes_array_t::FreeAll((_attributes_array_t *)&v13);
  v8 = 144 * v6;
  v9 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(144 * v6);
  v14 = v9;
  v10 = v9;
  if ( !v9 )
  {
    v7 = -2147024882;
    goto LABEL_13;
  }
  for ( ; v8; --v8 )
  {
    LOBYTE(v9->pwszName) = 0;
    v9 = (struct tagHELPER_ATTRIBUTE *)((char *)v9 + 1);
  }
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 6); i = (unsigned int)(i + 1) )
    _attribute_t::Copy(&v10[i], (const struct tagHELPER_ATTRIBUTE *)(144 * i + *((_QWORD *)this + 4)));
  *a2 = v6;
  *a3 = v10;
  v14 = 0;
  v13 = 0;
  _attributes_array_t::FreeAll((_attributes_array_t *)&v13);
  return 0;
}

```

## disassembly

```asm
0x18000bfe0  push    rbx
0x18000bfe2  push    rbp
0x18000bfe3  push    rsi
0x18000bfe4  push    rdi
0x18000bfe5  push    r14
0x18000bfe7  push    r15
0x18000bfe9  sub     rsp, 38h
0x18000bfed  mov     rsi, r8
0x18000bff0  mov     r14, rdx
0x18000bff3  mov     rdi, rcx
0x18000bff6  test    rdx, rdx
0x18000bff9  jnz     short loc_18000C000
0x18000bffb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c000  test    rsi, rsi
0x18000c003  jnz     short loc_18000C00A
0x18000c005  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c00a  cmp     dword ptr [rdi+10h], 1
0x18000c00e  jz      short loc_18000C015
0x18000c010  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c015  test    r14, r14
0x18000c018  jz      loc_18000C0E0
0x18000c01e  test    rsi, rsi
0x18000c021  jz      loc_18000C0E0
0x18000c027  mov     r15d, [rdi+18h]
0x18000c02b  mov     [rsp+68h+var_48], 0
0x18000c033  mov     [rsp+68h+var_40], 0
0x18000c03c  cmp     r15d, 1C71C71h
0x18000c043  jbe     short loc_18000C04C
0x18000c045  mov     ebx, 80070216h
0x18000c04a  jmp     short loc_18000C079
0x18000c04c  lea     rcx, [rsp+68h+var_48]; this
0x18000c051  call    ?FreeAll@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeAll(void)
0x18000c056  lea     rbx, [r15+r15*8]
0x18000c05a  shl     rbx, 4
0x18000c05e  mov     rcx, rbx; cb
0x18000c061  call    cs:__imp_CoTaskMemAlloc
0x18000c067  mov     [rsp+68h+var_40], rax
0x18000c06c  mov     rbp, rax
0x18000c06f  test    rax, rax
0x18000c072  jnz     short loc_18000C085
0x18000c074  mov     ebx, 8007000Eh
0x18000c079  lea     rcx, [rsp+68h+var_48]; this
0x18000c07e  call    ?FreeAll@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeAll(void)
0x18000c083  jmp     short loc_18000C0E5
0x18000c085  test    rbx, rbx
0x18000c088  jz      short loc_18000C096
0x18000c08a  mov     byte ptr [rax], 0
0x18000c08d  inc     rax
0x18000c090  sub     rbx, 1
0x18000c094  jnz     short loc_18000C08A
0x18000c096  xor     ebx, ebx
0x18000c098  cmp     [rdi+18h], ebx
0x18000c09b  jbe     short loc_18000C0BB
0x18000c09d  mov     rdx, [rdi+20h]
0x18000c0a1  lea     rcx, [rbx+rbx*8]
0x18000c0a5  shl     rcx, 4
0x18000c0a9  add     rdx, rcx; struct tagHELPER_ATTRIBUTE *
0x18000c0ac  add     rcx, rbp; this
0x18000c0af  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x18000c0b4  inc     ebx
0x18000c0b6  cmp     ebx, [rdi+18h]
0x18000c0b9  jb      short loc_18000C09D
0x18000c0bb  mov     [r14], r15d
0x18000c0be  lea     rcx, [rsp+68h+var_48]; this
0x18000c0c3  mov     [rsi], rbp
0x18000c0c6  mov     [rsp+68h+var_40], 0
0x18000c0cf  mov     [rsp+68h+var_48], 0
0x18000c0d7  call    ?FreeAll@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeAll(void)
0x18000c0dc  xor     ebx, ebx
0x18000c0de  jmp     short loc_18000C0E5
0x18000c0e0  mov     ebx, 80070057h
0x18000c0e5  mov     eax, ebx
0x18000c0e7  add     rsp, 38h
0x18000c0eb  pop     r15
0x18000c0ed  pop     r14
0x18000c0ef  pop     rdi
0x18000c0f0  pop     rsi
0x18000c0f1  pop     rbp
0x18000c0f2  pop     rbx
0x18000c0f3  retn
```
