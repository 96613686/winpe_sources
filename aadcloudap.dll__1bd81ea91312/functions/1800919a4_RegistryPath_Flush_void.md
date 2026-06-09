# RegistryPath::Flush(void)

- ea: `0x1800919a4`
- end: `0x180091b49`
- name: `?Flush@RegistryPath@@QEAAKXZ`
- size: `421`
- prototype: `unsigned int __fastcall(RegistryPath *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18008c778`

## callees

- `0x180086728`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aad8`
- `0x18008afb0`
- `0x1800919a4`
- `0x180092760`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180091a49`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180091a49`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180091ad2`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180091ad2`

## string_xrefs

- `0x180091a2a`: `%s: Failed to flush registry key "%s". Error code: 0x%08x.`
- `0x180091a96`: `%s: Failed to flush registry key "%s". Error code: 0x%08x.`
- `0x180091b03`: `%s: Failed to flush registry key "%s". Error code: 0x%08x.`
- `0x180091b2b`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x1800919df`: `RegistryPath::Flush`
- `0x180091b24`: `RegistryPath::Flush`

## pseudocode

```c
__int64 __fastcall RegistryPath::Flush(HKEY *this)
{
  unsigned int v2; // edi
  const unsigned __int16 *v3; // rax
  RegistryPath *v4; // rcx
  const unsigned __int16 *v5; // rax
  __int64 v6; // rcx
  const unsigned __int16 *v7; // r8
  unsigned int v8; // eax
  HKEY v9; // r8
  const wchar_t *v10; // rax
  wchar_t *v11; // rax
  wchar_t *v12; // r14
  const unsigned __int16 *v13; // rax
  unsigned int v14; // eax
  HKEY v15; // r8
  const unsigned __int16 *v16; // rax
  HKEY v17; // r9
  __int16 v18; // bp
  LSTATUS v19; // eax
  const unsigned __int16 *v20; // r8

  if ( this[4] && *this && *(_WORD *)*this )
  {
    v2 = 0;
    v3 = RegistryPath::SubPath((RegistryPath *)this);
    if ( v3 && *v3 )
    {
      v5 = RegistryPath::SubPath(v4);
      v8 = RegFlush(*(HKEY *)(v6 + 32), v5, v7);
      v9 = *this;
      v2 = v8;
      if ( v8 )
      {
        Logger::TraceWarning(
          L"%s: Failed to flush registry key \"%s\". Error code: 0x%08x.",
          L"RegistryPath::Flush",
          v9,
          v8);
        v10 = RegistryPath::SubPath((RegistryPath *)this);
        v11 = wcschr(v10, 0x5Cu);
        v12 = v11;
        if ( !v11 || !v11[1] )
          goto LABEL_16;
        *v11 = 0;
        v13 = RegistryPath::SubPath((RegistryPath *)this);
        v14 = RegFlush(this[4], v13, (const unsigned __int16 *)*this);
        v15 = *this;
        v2 = v14;
        if ( v14 )
          Logger::TraceWarning(
            L"%s: Failed to flush registry key \"%s\". Error code: 0x%08x.",
            L"RegistryPath::Flush",
            v15,
            v14);
        else
          Logger::TraceVerbose(L"%s: Successfully flushed reg key \"%s\".", L"RegistryPath::Flush", v15);
        *v12 = 92;
        if ( v2 )
          goto LABEL_16;
      }
      else
      {
        Logger::TraceVerbose(L"%s: Successfully flushed reg key \"%s\".", L"RegistryPath::Flush", v9);
      }
    }
    v16 = RegistryPath::SubPath((RegistryPath *)this);
    if ( v16 && *v16 )
      return v2;
LABEL_16:
    v17 = this[3];
    v18 = *((_WORD *)*this + (_QWORD)v17);
    *((_WORD *)*this + (_QWORD)v17) = 0;
    v19 = RegFlushKey(this[4]);
    v20 = (const unsigned __int16 *)*this;
    v2 = v19;
    if ( v19 )
    {
      Logger::WriteRegistryFailureEvent(v19, L"RegFlushKey", v20);
      Logger::TraceError(
        L"%s: Failed to flush registry key \"%s\". Error code: 0x%08x.",
        L"RegistryPath::Flush",
        *this,
        v2);
    }
    else
    {
      Logger::TraceVerbose(L"%s: Successfully flushed reg key \"%s\".", L"RegistryPath::Flush", v20);
    }
    *((_WORD *)*this + (_QWORD)this[3]) = v18;
    return v2;
  }
  Logger::TraceError(
    L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
    L"RegistryPath::Flush");
  return 87;
}

```

## disassembly

```asm
0x1800919a4  push    rbx
0x1800919a6  push    rbp
0x1800919a7  push    rsi
0x1800919a8  push    rdi
0x1800919a9  push    r14
0x1800919ab  push    r15
0x1800919ad  sub     rsp, 28h
0x1800919b1  xor     r15d, r15d
0x1800919b4  mov     rbx, rcx
0x1800919b7  cmp     [rcx+20h], r15
0x1800919bb  jz      loc_180091B24
0x1800919c1  mov     r8, [rcx]
0x1800919c4  test    r8, r8
0x1800919c7  jz      loc_180091B24
0x1800919cd  cmp     [r8], r15w
0x1800919d1  jz      loc_180091B24
0x1800919d7  mov     edi, r15d
0x1800919da  call    ?SubPath@RegistryPath@@QEBAPEBGXZ; RegistryPath::SubPath(void)
0x1800919df  lea     rsi, aRegistrypathFl; "RegistryPath::Flush"
0x1800919e6  test    rax, rax
0x1800919e9  jz      loc_180091AAA
0x1800919ef  cmp     [rax], r15w
0x1800919f3  jz      loc_180091AAA
0x1800919f9  call    ?SubPath@RegistryPath@@QEBAPEBGXZ; RegistryPath::SubPath(void)
0x1800919fe  mov     rcx, [rcx+20h]; HKEY
0x180091a02  mov     rdx, rax; unsigned __int16 *
0x180091a05  call    ?RegFlush@@YAKPEAUHKEY__@@PEBG1@Z; RegFlush(HKEY__ *,ushort const *,ushort const *)
0x180091a0a  mov     r8, [rbx]
0x180091a0d  mov     edi, eax
0x180091a0f  mov     rdx, rsi
0x180091a12  test    eax, eax
0x180091a14  jnz     short loc_180091A27
0x180091a16  lea     rcx, aSSuccessfullyF; "%s: Successfully flushed reg key \"%s\""...
0x180091a1d  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180091a22  jmp     loc_180091AAA
0x180091a27  mov     r9d, eax
0x180091a2a  lea     rcx, aSFailedToFlush; "%s: Failed to flush registry key \"%s\""...
0x180091a31  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180091a36  mov     rcx, rbx; this
0x180091a39  mov     ebp, 5Ch ; '\'
0x180091a3e  call    ?SubPath@RegistryPath@@QEBAPEBGXZ; RegistryPath::SubPath(void)
0x180091a43  mov     rcx, rax; Str
0x180091a46  movzx   edx, bp; Ch
0x180091a49  call    cs:__imp_wcschr
0x180091a4f  mov     r14, rax
0x180091a52  test    rax, rax
0x180091a55  jz      short loc_180091ABD
0x180091a57  cmp     [rax+2], r15w
0x180091a5c  jz      short loc_180091ABD
0x180091a5e  mov     rcx, rbx; this
0x180091a61  mov     [rax], r15w
0x180091a65  call    ?SubPath@RegistryPath@@QEBAPEBGXZ; RegistryPath::SubPath(void)
0x180091a6a  mov     r8, [rbx]; unsigned __int16 *
0x180091a6d  mov     rdx, rax; unsigned __int16 *
0x180091a70  mov     rcx, [rbx+20h]; HKEY
0x180091a74  call    ?RegFlush@@YAKPEAUHKEY__@@PEBG1@Z; RegFlush(HKEY__ *,ushort const *,ushort const *)
0x180091a79  mov     r8, [rbx]
0x180091a7c  mov     edi, eax
0x180091a7e  mov     rdx, rsi
0x180091a81  test    eax, eax
0x180091a83  jnz     short loc_180091A93
0x180091a85  lea     rcx, aSSuccessfullyF; "%s: Successfully flushed reg key \"%s\""...
0x180091a8c  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180091a91  jmp     short loc_180091AA2
0x180091a93  mov     r9d, edi
0x180091a96  lea     rcx, aSFailedToFlush; "%s: Failed to flush registry key \"%s\""...
0x180091a9d  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180091aa2  mov     [r14], bp
0x180091aa6  test    edi, edi
0x180091aa8  jnz     short loc_180091ABD
0x180091aaa  mov     rcx, rbx; this
0x180091aad  call    ?SubPath@RegistryPath@@QEBAPEBGXZ; RegistryPath::SubPath(void)
0x180091ab2  test    rax, rax
0x180091ab5  jz      short loc_180091ABD
0x180091ab7  cmp     [rax], r15w
0x180091abb  jnz     short loc_180091B20
0x180091abd  mov     r9, [rbx+18h]
0x180091ac1  mov     r8, [rbx]
0x180091ac4  movzx   ebp, word ptr [r8+r9*2]
0x180091ac9  mov     [r8+r9*2], r15w
0x180091ace  mov     rcx, [rbx+20h]; hKey
0x180091ad2  call    cs:__imp_RegFlushKey
0x180091ad8  mov     r8, [rbx]; unsigned __int16 *
0x180091adb  mov     edi, eax
0x180091add  test    eax, eax
0x180091adf  jnz     short loc_180091AF2
0x180091ae1  mov     rdx, rsi
0x180091ae4  lea     rcx, aSSuccessfullyF; "%s: Successfully flushed reg key \"%s\""...
0x180091aeb  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180091af0  jmp     short loc_180091B15
0x180091af2  lea     rdx, aRegflushkey; "RegFlushKey"
0x180091af9  mov     ecx, edi; unsigned int
0x180091afb  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x180091b00  mov     r8, [rbx]
0x180091b03  lea     rcx, aSFailedToFlush; "%s: Failed to flush registry key \"%s\""...
0x180091b0a  mov     r9d, edi
0x180091b0d  mov     rdx, rsi
0x180091b10  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180091b15  mov     rcx, [rbx+18h]
0x180091b19  mov     rax, [rbx]
0x180091b1c  mov     [rax+rcx*2], bp
0x180091b20  mov     eax, edi
0x180091b22  jmp     short loc_180091B3C
0x180091b24  lea     rdx, aRegistrypathFl; "RegistryPath::Flush"
0x180091b2b  lea     rcx, aSThisPathObjec; "%s: This path object has not been prope"...
0x180091b32  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180091b37  mov     eax, 57h ; 'W'
0x180091b3c  add     rsp, 28h
0x180091b40  pop     r15
0x180091b42  pop     r14
0x180091b44  pop     rdi
0x180091b45  pop     rsi
0x180091b46  pop     rbp
0x180091b47  pop     rbx
0x180091b48  retn
```
