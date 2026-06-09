# WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::Normalize(void)

- ea: `0x18002bc00`
- end: `0x18002beaa`
- name: `?Normalize@MidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@AEAAXXZ`
- size: `682`
- prototype: `void __fastcall(WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, registry_config, loader_planting, service_task`

## callers

- `0x18002af94`
- `0x18002c1e0`

## callees

- `0x1800052fc`
- `0x180005374`
- `0x180011240`
- `0x18002bc00`
- `0x18002beb0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002bd57`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002bd66`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002bd75`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002bdd3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002be96`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002bd57`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002bd66`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002bd75`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002bdd3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002be96`

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
0x18002bc00  push    rbp
0x18002bc02  push    rbx
0x18002bc03  push    rsi
0x18002bc04  push    rdi
0x18002bc05  push    r14
0x18002bc07  push    r15
0x18002bc09  mov     rbp, rsp
0x18002bc0c  sub     rsp, 28h
0x18002bc10  mov     rsi, rcx
0x18002bc13  mov     rdx, rcx
0x18002bc16  lea     rcx, [rbp+lpMem]
0x18002bc1a  call    ?TrimmedHStringCopy@WindowsMidiServicesInternal@@YA?AUhstring@winrt@@AEBU23@@Z; WindowsMidiServicesInternal::TrimmedHStringCopy(winrt::hstring const &)
0x18002bc1f  mov     rdx, rax
0x18002bc22  mov     rcx, rsi
0x18002bc25  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18002bc2a  mov     rbx, [rbp+lpMem]
0x18002bc2e  or      r15d, 0FFFFFFFFh
0x18002bc32  xor     r14d, r14d
0x18002bc35  test    rbx, rbx
0x18002bc38  jz      short loc_18002BC5E
0x18002bc3a  mov     eax, r15d
0x18002bc3d  lock xadd [rbx+18h], eax
0x18002bc42  sub     eax, 1
0x18002bc45  jnz     loc_18002BD4F
0x18002bc4b  nop
0x18002bc4c  call    WINRT_IMPL_GetProcessHeap
0x18002bc51  mov     rcx, rax; hHeap
0x18002bc54  mov     r8, rbx; lpMem
0x18002bc57  xor     edx, edx; dwFlags
0x18002bc59  call    WINRT_IMPL_HeapFree
0x18002bc5e  lea     rdx, [rsi+8]
0x18002bc62  lea     rcx, [rbp+lpMem]
0x18002bc66  call    ?TrimmedHStringCopy@WindowsMidiServicesInternal@@YA?AUhstring@winrt@@AEBU23@@Z; WindowsMidiServicesInternal::TrimmedHStringCopy(winrt::hstring const &)
0x18002bc6b  mov     rdx, rax
0x18002bc6e  lea     rcx, [rsi+8]
0x18002bc72  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18002bc77  mov     rbx, [rbp+lpMem]
0x18002bc7b  test    rbx, rbx
0x18002bc7e  jz      short loc_18002BCA4
0x18002bc80  mov     eax, r15d
0x18002bc83  lock xadd [rbx+18h], eax
0x18002bc88  sub     eax, 1
0x18002bc8b  jnz     loc_18002BD5E
0x18002bc91  nop
0x18002bc92  call    WINRT_IMPL_GetProcessHeap
0x18002bc97  mov     rcx, rax; hHeap
0x18002bc9a  mov     r8, rbx; lpMem
0x18002bc9d  xor     edx, edx; dwFlags
0x18002bc9f  call    WINRT_IMPL_HeapFree
0x18002bca4  lea     rdx, [rsi+10h]
0x18002bca8  lea     rcx, [rbp+lpMem]
0x18002bcac  call    ?TrimmedHStringCopy@WindowsMidiServicesInternal@@YA?AUhstring@winrt@@AEBU23@@Z; WindowsMidiServicesInternal::TrimmedHStringCopy(winrt::hstring const &)
0x18002bcb1  mov     rdx, rax
0x18002bcb4  lea     rcx, [rsi+10h]
0x18002bcb8  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18002bcbd  mov     rbx, [rbp+lpMem]
0x18002bcc1  test    rbx, rbx
0x18002bcc4  jz      short loc_18002BCEA
0x18002bcc6  mov     eax, r15d
0x18002bcc9  lock xadd [rbx+18h], eax
0x18002bcce  sub     eax, 1
0x18002bcd1  jnz     loc_18002BD6D
0x18002bcd7  nop
0x18002bcd8  call    WINRT_IMPL_GetProcessHeap
0x18002bcdd  mov     rcx, rax; hHeap
0x18002bce0  mov     r8, rbx; lpMem
0x18002bce3  xor     edx, edx; dwFlags
0x18002bce5  call    WINRT_IMPL_HeapFree
0x18002bcea  mov     rbx, [rsi+20h]
0x18002bcee  mov     rbx, [rbx]
0x18002bcf1  cmp     [rbx+19h], r14b
0x18002bcf5  jnz     loc_18002BDDA
0x18002bcfb  lea     rdi, [rbx+30h]
0x18002bcff  mov     rax, [rdi]
0x18002bd02  test    rax, rax
0x18002bd05  jz      short loc_18002BD84
0x18002bd07  cmp     dword ptr [rax+4], 20h ; ' '
0x18002bd0b  jbe     short loc_18002BD84
0x18002bd0d  mov     rdx, rdi
0x18002bd10  lea     rcx, [rbp+lpMem]
0x18002bd14  call    ?TruncateHStringCopy@WindowsMidiServicesInternal@@YA?AUhstring@winrt@@AEBU23@I@Z; WindowsMidiServicesInternal::TruncateHStringCopy(winrt::hstring const &,uint)
0x18002bd19  mov     rdx, rax
0x18002bd1c  mov     rcx, rdi
0x18002bd1f  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18002bd24  mov     rdi, [rbp+lpMem]
0x18002bd28  test    rdi, rdi
0x18002bd2b  jz      short loc_18002BD84
0x18002bd2d  mov     eax, r15d
0x18002bd30  lock xadd [rdi+18h], eax
0x18002bd35  sub     eax, 1
0x18002bd38  jnz     short loc_18002BD7C
0x18002bd3a  nop
0x18002bd3b  call    WINRT_IMPL_GetProcessHeap
0x18002bd40  mov     rcx, rax; hHeap
0x18002bd43  mov     r8, rdi; lpMem
0x18002bd46  xor     edx, edx; dwFlags
0x18002bd48  call    WINRT_IMPL_HeapFree
0x18002bd4d  jmp     short loc_18002BD80
0x18002bd4f  test    eax, eax
0x18002bd51  jns     loc_18002BC5E
0x18002bd57  call    cs:__imp_abort
0x18002bd5e  test    eax, eax
0x18002bd60  jns     loc_18002BCA4
0x18002bd66  call    cs:__imp_abort
0x18002bd6d  test    eax, eax
0x18002bd6f  jns     loc_18002BCEA
0x18002bd75  call    cs:__imp_abort
0x18002bd7c  test    eax, eax
0x18002bd7e  js      short loc_18002BDD3
0x18002bd80  mov     [rbp+lpMem], r14
0x18002bd84  mov     rcx, [rbx+10h]
0x18002bd88  cmp     [rcx+19h], r14b
0x18002bd8c  jz      short loc_18002BDAF
0x18002bd8e  mov     rax, [rbx+8]
0x18002bd92  jmp     short loc_18002BDA1
0x18002bd94  cmp     rbx, [rax+10h]
0x18002bd98  jnz     short loc_18002BDA7
0x18002bd9a  mov     rbx, rax
0x18002bd9d  mov     rax, [rax+8]
0x18002bda1  cmp     [rax+19h], r14b
0x18002bda5  jz      short loc_18002BD94
0x18002bda7  mov     rbx, rax
0x18002bdaa  jmp     loc_18002BCF1
0x18002bdaf  mov     rbx, rcx
0x18002bdb2  mov     rcx, [rcx]
0x18002bdb5  cmp     [rcx+19h], r14b
0x18002bdb9  jnz     loc_18002BCF1
0x18002bdbf  mov     rax, [rcx]
0x18002bdc2  mov     rbx, rcx
0x18002bdc5  mov     rcx, rax
0x18002bdc8  cmp     [rax+19h], r14b
0x18002bdcc  jz      short loc_18002BDBF
0x18002bdce  jmp     loc_18002BCF1
0x18002bdd3  call    cs:__imp_abort
0x18002bdda  mov     rbx, [rsi+30h]
0x18002bdde  mov     rbx, [rbx]
0x18002bde1  cmp     [rbx+19h], r14b
0x18002bde5  jnz     loc_18002BE9D
0x18002bdeb  lea     rdi, [rbx+30h]
0x18002bdef  mov     rax, [rdi]
0x18002bdf2  test    rax, rax
0x18002bdf5  jz      short loc_18002BE47
0x18002bdf7  cmp     dword ptr [rax+4], 20h ; ' '
0x18002bdfb  jbe     short loc_18002BE47
0x18002bdfd  mov     rdx, rdi
0x18002be00  lea     rcx, [rbp+lpMem]
0x18002be04  call    ?TruncateHStringCopy@WindowsMidiServicesInternal@@YA?AUhstring@winrt@@AEBU23@I@Z; WindowsMidiServicesInternal::TruncateHStringCopy(winrt::hstring const &,uint)
0x18002be09  mov     rdx, rax
0x18002be0c  mov     rcx, rdi
0x18002be0f  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18002be14  mov     rdi, [rbp+lpMem]
0x18002be18  test    rdi, rdi
0x18002be1b  jz      short loc_18002BE47
0x18002be1d  mov     eax, r15d
0x18002be20  lock xadd [rdi+18h], eax
0x18002be25  sub     eax, 1
0x18002be28  jnz     short loc_18002BE3F
0x18002be2a  nop
0x18002be2b  call    WINRT_IMPL_GetProcessHeap
0x18002be30  mov     rcx, rax; hHeap
0x18002be33  mov     r8, rdi; lpMem
0x18002be36  xor     edx, edx; dwFlags
0x18002be38  call    WINRT_IMPL_HeapFree
0x18002be3d  jmp     short loc_18002BE43
0x18002be3f  test    eax, eax
0x18002be41  js      short loc_18002BE96
0x18002be43  mov     [rbp+lpMem], r14
0x18002be47  mov     rcx, [rbx+10h]
0x18002be4b  cmp     [rcx+19h], r14b
0x18002be4f  jz      short loc_18002BE72
0x18002be51  mov     rax, [rbx+8]
0x18002be55  jmp     short loc_18002BE64
0x18002be57  cmp     rbx, [rax+10h]
0x18002be5b  jnz     short loc_18002BE6A
0x18002be5d  mov     rbx, rax
0x18002be60  mov     rax, [rax+8]
0x18002be64  cmp     [rax+19h], r14b
0x18002be68  jz      short loc_18002BE57
0x18002be6a  mov     rbx, rax
0x18002be6d  jmp     loc_18002BDE1
0x18002be72  mov     rbx, rcx
0x18002be75  mov     rcx, [rcx]
0x18002be78  cmp     [rcx+19h], r14b
0x18002be7c  jnz     loc_18002BDE1
0x18002be82  mov     rax, [rcx]
0x18002be85  mov     rbx, rcx
0x18002be88  mov     rcx, rax
0x18002be8b  cmp     [rax+19h], r14b
0x18002be8f  jz      short loc_18002BE82
0x18002be91  jmp     loc_18002BDE1
0x18002be96  call    cs:__imp_abort
0x18002be9d  add     rsp, 28h
0x18002bea1  pop     r15
0x18002bea3  pop     r14
0x18002bea5  pop     rdi
0x18002bea6  pop     rsi
0x18002bea7  pop     rbx
0x18002bea8  pop     rbp
0x18002bea9  retn
```
