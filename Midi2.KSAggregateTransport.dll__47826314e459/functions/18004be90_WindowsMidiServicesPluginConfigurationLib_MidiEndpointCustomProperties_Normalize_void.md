# WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::Normalize(void)

- ea: `0x18004be90`
- end: `0x18004c13a`
- name: `?Normalize@MidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@AEAAXXZ`
- size: `682`
- prototype: `void __fastcall(WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, registry_config, loader_planting, service_task`

## callers

- `0x18004b224`
- `0x18004c470`

## callees

- `0x180005f2c`
- `0x180005fa4`
- `0x180014f84`
- `0x18004be90`
- `0x18004c140`
- `0x18004c2a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004bfe7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004bff6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004c005`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004c063`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004c126`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004bfe7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004bff6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004c005`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004c063`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004c126`

## pseudocode

```c
void __fastcall WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::Normalize(
        WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties *this)
{
  winrt::hstring *v2; // rax
  void *v3; // rbx
  int v4; // eax
  HANDLE ProcessHeap; // rax
  winrt::hstring *v6; // rax
  void *v7; // rbx
  int v8; // eax
  HANDLE v9; // rax
  winrt::hstring *v10; // rax
  void *v11; // rbx
  int v12; // eax
  HANDLE v13; // rax
  __int64 *v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  void *v17; // rdi
  int v18; // eax
  HANDLE v19; // rax
  __int64 **v20; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 *v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rax
  void *v26; // rdi
  int v27; // eax
  HANDLE v28; // rax
  __int64 **v29; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  LPVOID lpMem; // [rsp+60h] [rbp+38h] BYREF

  v2 = WindowsMidiServicesInternal::TrimmedHStringCopy((winrt::hstring *)&lpMem, (__int64)this);
  winrt::hstring::operator=(this, v2);
  v3 = lpMem;
  if ( lpMem )
  {
    v4 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v4 )
    {
      if ( v4 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v3);
    }
  }
  v6 = WindowsMidiServicesInternal::TrimmedHStringCopy((winrt::hstring *)&lpMem, (__int64)this + 8);
  winrt::hstring::operator=((char *)this + 8, v6);
  v7 = lpMem;
  if ( lpMem )
  {
    v8 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v8 )
    {
      if ( v8 < 0 )
        abort();
    }
    else
    {
      v9 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v9, 0, v7);
    }
  }
  v10 = WindowsMidiServicesInternal::TrimmedHStringCopy((winrt::hstring *)&lpMem, (__int64)this + 16);
  winrt::hstring::operator=((char *)this + 16, v10);
  v11 = lpMem;
  if ( lpMem )
  {
    v12 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v12 )
    {
      if ( v12 < 0 )
        abort();
    }
    else
    {
      v13 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v13, 0, v11);
    }
  }
  v14 = (__int64 *)**((_QWORD **)this + 4);
  while ( !*((_BYTE *)v14 + 25) )
  {
    v15 = v14[6];
    if ( v15 )
    {
      if ( *(_DWORD *)(v15 + 4) > 0x20u )
      {
        v16 = WindowsMidiServicesInternal::TruncateHStringCopy(&lpMem, v14 + 6);
        winrt::hstring::operator=(v14 + 6, v16);
        v17 = lpMem;
        if ( lpMem )
        {
          v18 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
          if ( v18 )
          {
            if ( v18 < 0 )
              abort();
          }
          else
          {
            v19 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v19, 0, v17);
          }
          lpMem = 0;
        }
      }
    }
    v20 = (__int64 **)v14[2];
    if ( *((_BYTE *)v20 + 25) )
    {
      for ( i = (__int64 *)v14[1]; !*((_BYTE *)i + 25) && v14 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v14 = i;
      v14 = i;
    }
    else
    {
      v14 = (__int64 *)v14[2];
      for ( j = *v20; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v14 = j;
    }
  }
  v23 = (__int64 *)**((_QWORD **)this + 6);
  while ( !*((_BYTE *)v23 + 25) )
  {
    v24 = v23[6];
    if ( v24 )
    {
      if ( *(_DWORD *)(v24 + 4) > 0x20u )
      {
        v25 = WindowsMidiServicesInternal::TruncateHStringCopy(&lpMem, v23 + 6);
        winrt::hstring::operator=(v23 + 6, v25);
        v26 = lpMem;
        if ( lpMem )
        {
          v27 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
          if ( v27 )
          {
            if ( v27 < 0 )
              abort();
          }
          else
          {
            v28 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v28, 0, v26);
          }
          lpMem = 0;
        }
      }
    }
    v29 = (__int64 **)v23[2];
    if ( *((_BYTE *)v29 + 25) )
    {
      for ( k = (__int64 *)v23[1]; !*((_BYTE *)k + 25) && v23 == (__int64 *)k[2]; k = (__int64 *)k[1] )
        v23 = k;
      v23 = k;
    }
    else
    {
      v23 = (__int64 *)v23[2];
      for ( m = *v29; !*((_BYTE *)m + 25); m = (__int64 *)*m )
        v23 = m;
    }
  }
}

```

## disassembly

```asm
0x18004be90  push    rbp
0x18004be92  push    rbx
0x18004be93  push    rsi
0x18004be94  push    rdi
0x18004be95  push    r14
0x18004be97  push    r15
0x18004be99  mov     rbp, rsp
0x18004be9c  sub     rsp, 28h
0x18004bea0  mov     rsi, rcx
0x18004bea3  mov     rdx, rcx
0x18004bea6  lea     rcx, [rbp+lpMem]
0x18004beaa  call    ?TrimmedHStringCopy@WindowsMidiServicesInternal@@YA?AUhstring@winrt@@AEBU23@@Z; WindowsMidiServicesInternal::TrimmedHStringCopy(winrt::hstring const &)
0x18004beaf  mov     rdx, rax
0x18004beb2  mov     rcx, rsi
0x18004beb5  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18004beba  mov     rbx, [rbp+lpMem]
0x18004bebe  or      r15d, 0FFFFFFFFh
0x18004bec2  xor     r14d, r14d
0x18004bec5  test    rbx, rbx
0x18004bec8  jz      short loc_18004BEEE
0x18004beca  mov     eax, r15d
0x18004becd  lock xadd [rbx+18h], eax
0x18004bed2  sub     eax, 1
0x18004bed5  jnz     loc_18004BFDF
0x18004bedb  nop
0x18004bedc  call    WINRT_IMPL_GetProcessHeap
0x18004bee1  mov     rcx, rax; hHeap
0x18004bee4  mov     r8, rbx; lpMem
0x18004bee7  xor     edx, edx; dwFlags
0x18004bee9  call    WINRT_IMPL_HeapFree
0x18004beee  lea     rdx, [rsi+8]
0x18004bef2  lea     rcx, [rbp+lpMem]
0x18004bef6  call    ?TrimmedHStringCopy@WindowsMidiServicesInternal@@YA?AUhstring@winrt@@AEBU23@@Z; WindowsMidiServicesInternal::TrimmedHStringCopy(winrt::hstring const &)
0x18004befb  mov     rdx, rax
0x18004befe  lea     rcx, [rsi+8]
0x18004bf02  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18004bf07  mov     rbx, [rbp+lpMem]
0x18004bf0b  test    rbx, rbx
0x18004bf0e  jz      short loc_18004BF34
0x18004bf10  mov     eax, r15d
0x18004bf13  lock xadd [rbx+18h], eax
0x18004bf18  sub     eax, 1
0x18004bf1b  jnz     loc_18004BFEE
0x18004bf21  nop
0x18004bf22  call    WINRT_IMPL_GetProcessHeap
0x18004bf27  mov     rcx, rax; hHeap
0x18004bf2a  mov     r8, rbx; lpMem
0x18004bf2d  xor     edx, edx; dwFlags
0x18004bf2f  call    WINRT_IMPL_HeapFree
0x18004bf34  lea     rdx, [rsi+10h]
0x18004bf38  lea     rcx, [rbp+lpMem]
0x18004bf3c  call    ?TrimmedHStringCopy@WindowsMidiServicesInternal@@YA?AUhstring@winrt@@AEBU23@@Z; WindowsMidiServicesInternal::TrimmedHStringCopy(winrt::hstring const &)
0x18004bf41  mov     rdx, rax
0x18004bf44  lea     rcx, [rsi+10h]
0x18004bf48  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18004bf4d  mov     rbx, [rbp+lpMem]
0x18004bf51  test    rbx, rbx
0x18004bf54  jz      short loc_18004BF7A
0x18004bf56  mov     eax, r15d
0x18004bf59  lock xadd [rbx+18h], eax
0x18004bf5e  sub     eax, 1
0x18004bf61  jnz     loc_18004BFFD
0x18004bf67  nop
0x18004bf68  call    WINRT_IMPL_GetProcessHeap
0x18004bf6d  mov     rcx, rax; hHeap
0x18004bf70  mov     r8, rbx; lpMem
0x18004bf73  xor     edx, edx; dwFlags
0x18004bf75  call    WINRT_IMPL_HeapFree
0x18004bf7a  mov     rbx, [rsi+20h]
0x18004bf7e  mov     rbx, [rbx]
0x18004bf81  cmp     [rbx+19h], r14b
0x18004bf85  jnz     loc_18004C06A
0x18004bf8b  lea     rdi, [rbx+30h]
0x18004bf8f  mov     rax, [rdi]
0x18004bf92  test    rax, rax
0x18004bf95  jz      short loc_18004C014
0x18004bf97  cmp     dword ptr [rax+4], 20h ; ' '
0x18004bf9b  jbe     short loc_18004C014
0x18004bf9d  mov     rdx, rdi
0x18004bfa0  lea     rcx, [rbp+lpMem]
0x18004bfa4  call    ?TruncateHStringCopy@WindowsMidiServicesInternal@@YA?AUhstring@winrt@@AEBU23@I@Z; WindowsMidiServicesInternal::TruncateHStringCopy(winrt::hstring const &,uint)
0x18004bfa9  mov     rdx, rax
0x18004bfac  mov     rcx, rdi
0x18004bfaf  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18004bfb4  mov     rdi, [rbp+lpMem]
0x18004bfb8  test    rdi, rdi
0x18004bfbb  jz      short loc_18004C014
0x18004bfbd  mov     eax, r15d
0x18004bfc0  lock xadd [rdi+18h], eax
0x18004bfc5  sub     eax, 1
0x18004bfc8  jnz     short loc_18004C00C
0x18004bfca  nop
0x18004bfcb  call    WINRT_IMPL_GetProcessHeap
0x18004bfd0  mov     rcx, rax; hHeap
0x18004bfd3  mov     r8, rdi; lpMem
0x18004bfd6  xor     edx, edx; dwFlags
0x18004bfd8  call    WINRT_IMPL_HeapFree
0x18004bfdd  jmp     short loc_18004C010
0x18004bfdf  test    eax, eax
0x18004bfe1  jns     loc_18004BEEE
0x18004bfe7  call    cs:__imp_abort
0x18004bfee  test    eax, eax
0x18004bff0  jns     loc_18004BF34
0x18004bff6  call    cs:__imp_abort
0x18004bffd  test    eax, eax
0x18004bfff  jns     loc_18004BF7A
0x18004c005  call    cs:__imp_abort
0x18004c00c  test    eax, eax
0x18004c00e  js      short loc_18004C063
0x18004c010  mov     [rbp+lpMem], r14
0x18004c014  mov     rcx, [rbx+10h]
0x18004c018  cmp     [rcx+19h], r14b
0x18004c01c  jz      short loc_18004C03F
0x18004c01e  mov     rax, [rbx+8]
0x18004c022  jmp     short loc_18004C031
0x18004c024  cmp     rbx, [rax+10h]
0x18004c028  jnz     short loc_18004C037
0x18004c02a  mov     rbx, rax
0x18004c02d  mov     rax, [rax+8]
0x18004c031  cmp     [rax+19h], r14b
0x18004c035  jz      short loc_18004C024
0x18004c037  mov     rbx, rax
0x18004c03a  jmp     loc_18004BF81
0x18004c03f  mov     rbx, rcx
0x18004c042  mov     rcx, [rcx]
0x18004c045  cmp     [rcx+19h], r14b
0x18004c049  jnz     loc_18004BF81
0x18004c04f  mov     rax, [rcx]
0x18004c052  mov     rbx, rcx
0x18004c055  mov     rcx, rax
0x18004c058  cmp     [rax+19h], r14b
0x18004c05c  jz      short loc_18004C04F
0x18004c05e  jmp     loc_18004BF81
0x18004c063  call    cs:__imp_abort
0x18004c06a  mov     rbx, [rsi+30h]
0x18004c06e  mov     rbx, [rbx]
0x18004c071  cmp     [rbx+19h], r14b
0x18004c075  jnz     loc_18004C12D
0x18004c07b  lea     rdi, [rbx+30h]
0x18004c07f  mov     rax, [rdi]
0x18004c082  test    rax, rax
0x18004c085  jz      short loc_18004C0D7
0x18004c087  cmp     dword ptr [rax+4], 20h ; ' '
0x18004c08b  jbe     short loc_18004C0D7
0x18004c08d  mov     rdx, rdi
0x18004c090  lea     rcx, [rbp+lpMem]
0x18004c094  call    ?TruncateHStringCopy@WindowsMidiServicesInternal@@YA?AUhstring@winrt@@AEBU23@I@Z; WindowsMidiServicesInternal::TruncateHStringCopy(winrt::hstring const &,uint)
0x18004c099  mov     rdx, rax
0x18004c09c  mov     rcx, rdi
0x18004c09f  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18004c0a4  mov     rdi, [rbp+lpMem]
0x18004c0a8  test    rdi, rdi
0x18004c0ab  jz      short loc_18004C0D7
0x18004c0ad  mov     eax, r15d
0x18004c0b0  lock xadd [rdi+18h], eax
0x18004c0b5  sub     eax, 1
0x18004c0b8  jnz     short loc_18004C0CF
0x18004c0ba  nop
0x18004c0bb  call    WINRT_IMPL_GetProcessHeap
0x18004c0c0  mov     rcx, rax; hHeap
0x18004c0c3  mov     r8, rdi; lpMem
0x18004c0c6  xor     edx, edx; dwFlags
0x18004c0c8  call    WINRT_IMPL_HeapFree
0x18004c0cd  jmp     short loc_18004C0D3
0x18004c0cf  test    eax, eax
0x18004c0d1  js      short loc_18004C126
0x18004c0d3  mov     [rbp+lpMem], r14
0x18004c0d7  mov     rcx, [rbx+10h]
0x18004c0db  cmp     [rcx+19h], r14b
0x18004c0df  jz      short loc_18004C102
0x18004c0e1  mov     rax, [rbx+8]
0x18004c0e5  jmp     short loc_18004C0F4
0x18004c0e7  cmp     rbx, [rax+10h]
0x18004c0eb  jnz     short loc_18004C0FA
0x18004c0ed  mov     rbx, rax
0x18004c0f0  mov     rax, [rax+8]
0x18004c0f4  cmp     [rax+19h], r14b
0x18004c0f8  jz      short loc_18004C0E7
0x18004c0fa  mov     rbx, rax
0x18004c0fd  jmp     loc_18004C071
0x18004c102  mov     rbx, rcx
0x18004c105  mov     rcx, [rcx]
0x18004c108  cmp     [rcx+19h], r14b
0x18004c10c  jnz     loc_18004C071
0x18004c112  mov     rax, [rcx]
0x18004c115  mov     rbx, rcx
0x18004c118  mov     rcx, rax
0x18004c11b  cmp     [rax+19h], r14b
0x18004c11f  jz      short loc_18004C112
0x18004c121  jmp     loc_18004C071
0x18004c126  call    cs:__imp_abort
0x18004c12d  add     rsp, 28h
0x18004c131  pop     r15
0x18004c133  pop     r14
0x18004c135  pop     rdi
0x18004c136  pop     rsi
0x18004c137  pop     rbx
0x18004c138  pop     rbp
0x18004c139  retn
```
