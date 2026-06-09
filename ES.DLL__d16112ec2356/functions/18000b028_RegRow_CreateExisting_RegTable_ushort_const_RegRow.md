# RegRow::CreateExisting(RegTable *,ushort const *,RegRow * &)

- ea: `0x18000b028`
- end: `0x18000b155`
- name: `?CreateExisting@RegRow@@SAJPEAVRegTable@@PEBGAEAPEAV1@@Z`
- size: `301`
- prototype: `__int64 __fastcall(struct RegTable *, const unsigned __int16 *, struct RegRow **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009498`
- `0x18000d7a0`

## callees

- `0x180006194`
- `0x18000b028`
- `0x18000bbc8`
- `0x18000c910`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b0d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b0d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b0e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b0e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b07b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b07b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b12d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b12d`

## pseudocode

```c
__int64 __fastcall RegRow::CreateExisting(struct RegTable *a1, const unsigned __int16 *a2, struct RegRow **a3)
{
  const unsigned __int16 *v6; // rdx
  int v7; // eax
  int v8; // r9d
  unsigned int v9; // r12d
  unsigned __int16 *v10; // rax
  WCHAR *v11; // rdi
  int v12; // ebx
  HKEY v13; // rcx
  LSTATUS v14; // eax
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF

  safe_lstrlenW((const unsigned __int16 *)a1 + 9);
  v7 = safe_lstrlenW(v6);
  v9 = v8 + v7 + 2;
  v10 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v9, 2u));
  v11 = v10;
  if ( v10 )
  {
    v12 = StringCchPrintfW(v10, v9, L"%s\\%s", (char *)a1 + 18, a2);
    if ( v12 < 0 )
      goto LABEL_9;
    v13 = (HKEY)*((_QWORD *)a1 + 1);
    hKey = 0;
    v14 = RegOpenKeyExW(v13, v11, 0, 0x20019u, &hKey);
    v12 = v14;
    if ( v14 )
    {
      if ( v14 > 0 )
        v12 = (unsigned __int16)v14 | 0x80070000;
    }
    else
    {
      RegCloseKey(hKey);
      v12 = RegRow::Create(a1, v9, v11, a2, 0, 0, a3);
    }
    if ( v12 < 0 )
LABEL_9:
      CoTaskMemFree(v11);
    else
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000b028  mov     [rsp+arg_8], rbx
0x18000b02d  mov     [rsp+arg_10], rbp
0x18000b032  push    rsi
0x18000b033  push    rdi
0x18000b034  push    r12
0x18000b036  push    r14
0x18000b038  push    r15
0x18000b03a  sub     rsp, 40h
0x18000b03e  mov     rsi, rcx
0x18000b041  mov     r14, r8
0x18000b044  add     rcx, 12h; unsigned __int16 *
0x18000b048  mov     rbp, rdx
0x18000b04b  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18000b050  mov     rcx, rdx; unsigned __int16 *
0x18000b053  mov     r9d, eax
0x18000b056  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18000b05b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b062  lea     r12d, [rax+2]
0x18000b066  mov     eax, 2
0x18000b06b  add     r12d, r9d
0x18000b06e  mov     r15d, r12d
0x18000b071  mul     r15
0x18000b074  cmovb   rax, rcx
0x18000b078  mov     rcx, rax; cb
0x18000b07b  call    cs:__imp_CoTaskMemAlloc
0x18000b081  mov     rdi, rax
0x18000b084  test    rax, rax
0x18000b087  jz      loc_18000B135
0x18000b08d  lea     r9, [rsi+12h]
0x18000b091  mov     [rsp+68h+phkResult], rbp
0x18000b096  lea     r8, aSS; "%s\\%s"
0x18000b09d  mov     edx, r15d; unsigned __int64
0x18000b0a0  mov     rcx, rax; unsigned __int16 *
0x18000b0a3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b0a8  mov     ebx, eax
0x18000b0aa  test    eax, eax
0x18000b0ac  js      short loc_18000B12A
0x18000b0ae  mov     rcx, [rsi+8]; hKey
0x18000b0b2  lea     rax, [rsp+68h+hKey]
0x18000b0b7  mov     r9d, 20019h; samDesired
0x18000b0bd  mov     [rsp+68h+phkResult], rax; phkResult
0x18000b0c2  xor     r8d, r8d; ulOptions
0x18000b0c5  mov     [rsp+68h+hKey], 0
0x18000b0ce  mov     rdx, rdi; lpSubKey
0x18000b0d1  call    cs:__imp_RegOpenKeyExW
0x18000b0d7  mov     ebx, eax
0x18000b0d9  test    eax, eax
0x18000b0db  jnz     short loc_18000B10A
0x18000b0dd  mov     rcx, [rsp+68h+hKey]; hKey
0x18000b0e2  call    cs:__imp_RegCloseKey
0x18000b0e8  mov     [rsp+68h+var_38], r14; struct RegRow **
0x18000b0ed  mov     r9, rbp; unsigned __int16 *
0x18000b0f0  mov     [rsp+68h+var_40], bl; bool
0x18000b0f4  mov     r8, rdi; unsigned __int16 *
0x18000b0f7  mov     edx, r12d; unsigned int
0x18000b0fa  mov     byte ptr [rsp+68h+phkResult], bl; bool
0x18000b0fe  mov     rcx, rsi; struct RegTable *
0x18000b101  call    ?Create@RegRow@@CAJPEAVRegTable@@KPEAGPEBG_N3AEAPEAV1@@Z; RegRow::Create(RegTable *,ulong,ushort *,ushort const *,bool,bool,RegRow * &)
0x18000b106  mov     ebx, eax
0x18000b108  jmp     short loc_18000B115
0x18000b10a  jle     short loc_18000B115
0x18000b10c  movzx   ebx, ax
0x18000b10f  or      ebx, 80070000h
0x18000b115  test    ebx, ebx
0x18000b117  js      short loc_18000B12A
0x18000b119  mov     rcx, [r14]
0x18000b11c  mov     rax, [rcx]
0x18000b11f  mov     rax, [rax+8]
0x18000b123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b128  jmp     short loc_18000B13A
0x18000b12a  mov     rcx, rdi; pv
0x18000b12d  call    cs:__imp_CoTaskMemFree
0x18000b133  jmp     short loc_18000B13A
0x18000b135  mov     ebx, 8007000Eh
0x18000b13a  lea     r11, [rsp+68h+var_28]
0x18000b13f  mov     eax, ebx
0x18000b141  mov     rbx, [r11+38h]
0x18000b145  mov     rbp, [r11+40h]
0x18000b149  mov     rsp, r11
0x18000b14c  pop     r15
0x18000b14e  pop     r14
0x18000b150  pop     r12
0x18000b152  pop     rdi
0x18000b153  pop     rsi
0x18000b154  retn
```
