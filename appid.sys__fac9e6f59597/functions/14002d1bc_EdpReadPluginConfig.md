# EdpReadPluginConfig

- ea: `0x14002d1bc`
- end: `0x14002d2da`
- name: `EdpReadPluginConfig`
- size: `286`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x14002bf44`

## callees

- `0x14000421c`
- `0x1400293ac`
- `0x14002948c`
- `0x14002d1bc`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002d252`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002d252`

## string_xrefs

- `0x14002d1c8`: `\REGISTRY\MACHINE\System\CurrentControlSet\Control\AppID\Configuration\EDP`

## pseudocode

```c
char __fastcall EdpReadPluginConfig(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  size_t v4; // rdx
  const wchar_t *v5; // rdi
  size_t v6; // rsi
  __int64 v7; // rcx
  int v8; // eax
  struct _UNICODE_STRING v10; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING v11; // [rsp+30h] [rbp-18h] BYREF
  int v12; // [rsp+70h] [rbp+28h] BYREF

  *(_QWORD *)&v10.Length = 9830548;
  v10.Buffer = L"\\REGISTRY\\MACHINE\\System\\CurrentControlSet\\Control\\AppID\\Configuration\\EDP";
  *(_QWORD *)&v11.Length = 1572886;
  v11.Buffer = L"DataContext";
  v12 = 0;
  if ( (int)AiRegReadStringValue(0, &v10, &v11, a1 + 8) >= 0 )
  {
    v3 = AiAlloc(0xA0u);
    *(_QWORD *)(a1 + 24) = v3;
    if ( v3 )
    {
      v5 = *(const wchar_t **)(a1 + 16);
      *(_DWORD *)(a1 + 32) = 0;
      while ( *v5 )
      {
        v6 = wcsnlen_s(v5, v4);
        if ( !v6 )
        {
          *(_DWORD *)(a1 + 32) = 0;
          break;
        }
        RtlInitUnicodeString((PUNICODE_STRING)(*(_QWORD *)(a1 + 24) + 16LL * *(unsigned int *)(a1 + 32)), v5);
        ++*(_DWORD *)(a1 + 32);
        v5 += v6 + 1;
      }
    }
  }
  if ( (int)AiRegReadDwordValue(v2, (struct _UNICODE_STRING *)&qword_140009DD0, (struct _UNICODE_STRING *)L" \"", &v12) >= 0
    || (int)AiRegReadDwordValue(v7, &v10, (struct _UNICODE_STRING *)L" \"", &v12) >= 0 )
  {
    *(_DWORD *)(a1 + 4) = v12;
  }
  v8 = AiRegReadDwordValue(v7, &v10, (struct _UNICODE_STRING *)&qword_140009DC0, &v12);
  if ( v8 >= 0 )
  {
    LOBYTE(v8) = v12 != 0;
    *(_BYTE *)(a1 + 1) = v12 != 0;
  }
  *(_BYTE *)a1 = 1;
  return v8;
}

```

## disassembly

```asm
0x14002d1bc  push    rbp
0x14002d1be  push    rbx
0x14002d1bf  push    rsi
0x14002d1c0  push    rdi
0x14002d1c1  mov     rbp, rsp
0x14002d1c4  sub     rsp, 48h
0x14002d1c8  lea     rax, aRegistryMachin_2; "\\REGISTRY\\MACHINE\\System\\CurrentCon"...
0x14002d1cf  mov     [rbp+var_28], 960094h
0x14002d1d7  mov     [rbp+var_20], rax
0x14002d1db  lea     r9, [rcx+8]
0x14002d1df  lea     rax, aDatacontext; "DataContext"
0x14002d1e6  mov     [rbp+var_18], 180016h
0x14002d1ee  mov     rbx, rcx
0x14002d1f1  mov     [rbp+var_10], rax
0x14002d1f5  lea     r8, [rbp+var_18]
0x14002d1f9  mov     [rbp+arg_0], 0
0x14002d200  lea     rdx, [rbp+var_28]
0x14002d204  xor     ecx, ecx
0x14002d206  call    AiRegReadStringValue
0x14002d20b  test    eax, eax
0x14002d20d  js      short loc_14002D272
0x14002d20f  mov     ecx, 0A0h
0x14002d214  call    AiAlloc
0x14002d219  mov     [rbx+18h], rax
0x14002d21d  test    rax, rax
0x14002d220  jz      short loc_14002D272
0x14002d222  mov     rdi, [rbx+10h]
0x14002d226  mov     dword ptr [rbx+20h], 0
0x14002d22d  xor     eax, eax
0x14002d22f  cmp     ax, [rdi]
0x14002d232  jz      short loc_14002D272
0x14002d234  mov     rcx, rdi; Src
0x14002d237  call    wcsnlen_s
0x14002d23c  mov     rsi, rax
0x14002d23f  test    rax, rax
0x14002d242  jz      short loc_14002D26B
0x14002d244  mov     ecx, [rbx+20h]
0x14002d247  mov     rdx, rdi; SourceString
0x14002d24a  shl     rcx, 4
0x14002d24e  add     rcx, [rbx+18h]; DestinationString
0x14002d252  call    cs:__imp_RtlInitUnicodeString
0x14002d259  nop     dword ptr [rax+rax+00h]
0x14002d25e  inc     dword ptr [rbx+20h]
0x14002d261  lea     rdi, [rdi+rsi*2]
0x14002d265  add     rdi, 2
0x14002d269  jmp     short loc_14002D22D
0x14002d26b  mov     dword ptr [rbx+20h], 0
0x14002d272  lea     r9, [rbp+arg_0]
0x14002d276  lea     r8, asc_140009DE0; " \""
0x14002d27d  lea     rdx, qword_140009DD0
0x14002d284  call    AiRegReadDwordValue
0x14002d289  test    eax, eax
0x14002d28b  jns     short loc_14002D2A5
0x14002d28d  lea     r9, [rbp+arg_0]
0x14002d291  lea     r8, asc_140009DE0; " \""
0x14002d298  lea     rdx, [rbp+var_28]
0x14002d29c  call    AiRegReadDwordValue
0x14002d2a1  test    eax, eax
0x14002d2a3  js      short loc_14002D2AB
0x14002d2a5  mov     eax, [rbp+arg_0]
0x14002d2a8  mov     [rbx+4], eax
0x14002d2ab  lea     r9, [rbp+arg_0]
0x14002d2af  lea     r8, qword_140009DC0
0x14002d2b6  lea     rdx, [rbp+var_28]
0x14002d2ba  call    AiRegReadDwordValue
0x14002d2bf  test    eax, eax
0x14002d2c1  js      short loc_14002D2CD
0x14002d2c3  cmp     [rbp+arg_0], 0
0x14002d2c7  setnz   al
0x14002d2ca  mov     [rbx+1], al
0x14002d2cd  mov     byte ptr [rbx], 1
0x14002d2d0  add     rsp, 48h
0x14002d2d4  pop     rdi
0x14002d2d5  pop     rsi
0x14002d2d6  pop     rbx
0x14002d2d7  pop     rbp
0x14002d2d8  retn
```
