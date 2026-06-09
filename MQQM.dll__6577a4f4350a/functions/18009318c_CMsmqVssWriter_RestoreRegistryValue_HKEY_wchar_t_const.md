# CMsmqVssWriter::RestoreRegistryValue(HKEY__ *,wchar_t const *)

- ea: `0x18009318c`
- end: `0x180093313`
- name: `?RestoreRegistryValue@CMsmqVssWriter@@AEAAJPEAUHKEY__@@PEB_W@Z`
- size: `391`
- prototype: `int(CMsmqVssWriter *__hidden this, HKEY, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180092cb8`

## callees

- `0x18000cb80`
- `0x18002c61c`
- `0x18009318c`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x1800932ce`
- `msvcrt!free` at `0x1800932dc`
- `msvcrt!free` at `0x1800932ce`
- `msvcrt!free` at `0x1800932dc`
- `msvcrt!wcschr` at `0x1800931c1`
- `msvcrt!wcschr` at `0x1800931e9`
- `msvcrt!wcschr` at `0x1800931c1`
- `msvcrt!wcschr` at `0x1800931e9`
- `msvcrt!_snwscanf_s` at `0x180093224`
- `msvcrt!_snwscanf_s` at `0x18009326b`
- `msvcrt!_snwscanf_s` at `0x180093224`
- `msvcrt!_snwscanf_s` at `0x18009326b`
- `ADVAPI32!RegSetValueExW` at `0x18009329b`
- `ADVAPI32!RegSetValueExW` at `0x18009329b`

## string_xrefs

- `0x1800932bc`: `writer/mqwriter`
- `0x1800932f2`: `writer/mqwriter`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMsmqVssWriter::RestoreRegistryValue(CMsmqVssWriter *this, HKEY a2, const wchar_t *a3)
{
  wchar_t *v5; // rcx
  unsigned __int16 v6; // r8
  const wchar_t *v7; // rbx
  wchar_t *v8; // rdx
  const wchar_t *v9; // r15
  unsigned __int64 cbData; // r14
  BYTE *lpData; // rbx
  __int64 i; // rsi
  LSTATUS v13; // eax
  signed int v14; // edi
  CMsmqVssWriter *v16; // [rsp+60h] [rbp+8h] BYREF
  DWORD dwType; // [rsp+68h] [rbp+10h] BYREF
  BYTE *v18; // [rsp+78h] [rbp+20h]

  v16 = this;
  if ( !a2 || !a3 )
  {
    v6 = 2100;
    goto LABEL_17;
  }
  v5 = wcschr(a3, 0x3Du);
  if ( !v5 )
  {
    v6 = 2120;
LABEL_17:
    LogMsgHR(-1072824314, (wchar_t *)L"writer/mqwriter", v6);
    return 3222142982LL;
  }
  *v5 = 0;
  v7 = v5 + 1;
  v8 = wcschr(v5 + 1, 0x3Au);
  if ( !v8 )
  {
    v6 = 2140;
    goto LABEL_17;
  }
  *v8 = 0;
  v9 = v8 + 1;
  dwType = 0;
  _snwscanf_s(v7, v8 - v7, L"%u", &dwType);
  cbData = mqwcslen(v9) >> 1;
  lpData = (BYTE *)MmAllocate(cbData);
  v18 = lpData;
  for ( i = 0; (unsigned int)i < (unsigned int)cbData; v9 += 2 )
  {
    LODWORD(v16) = 0;
    _snwscanf_s(v9, 2u, L"%02x", &v16);
    lpData[i] = (unsigned __int8)v16;
    i = (unsigned int)(i + 1);
  }
  v13 = RegSetValueExW(a2, a3, 0, dwType, lpData, cbData);
  v14 = v13;
  if ( v13 )
  {
    if ( v13 > 0 )
      v14 = (unsigned __int16)v13 | 0x80070000;
    if ( v14 < 0 )
      LogMsgHR(v14, (wchar_t *)L"writer/mqwriter", 0x870u);
    free(lpData);
    return (unsigned int)v14;
  }
  else
  {
    free(lpData);
    return 0;
  }
}

```

## disassembly

```asm
0x18009318c  mov     [rsp+arg_10], rbx
0x180093191  mov     [rsp+arg_0], rcx
0x180093196  push    rbp
0x180093197  push    rsi
0x180093198  push    rdi
0x180093199  push    r14
0x18009319b  push    r15
0x18009319d  sub     rsp, 30h
0x1800931a1  mov     rdi, r8
0x1800931a4  mov     rbp, rdx
0x1800931a7  test    rdx, rdx
0x1800931aa  jz      loc_1800932E7
0x1800931b0  test    r8, r8
0x1800931b3  jz      loc_1800932E7
0x1800931b9  mov     edx, 3Dh ; '='; Ch
0x1800931be  mov     rcx, r8; Str
0x1800931c1  call    cs:__imp_wcschr
0x1800931c7  mov     rcx, rax
0x1800931ca  test    rax, rax
0x1800931cd  jnz     short loc_1800931DA
0x1800931cf  mov     r8d, 848h
0x1800931d5  jmp     loc_1800932ED
0x1800931da  xor     eax, eax
0x1800931dc  mov     [rcx], ax
0x1800931df  lea     rbx, [rcx+2]
0x1800931e3  lea     edx, [rax+3Ah]; Ch
0x1800931e6  mov     rcx, rbx; Str
0x1800931e9  call    cs:__imp_wcschr
0x1800931ef  mov     rdx, rax
0x1800931f2  test    rax, rax
0x1800931f5  jnz     short loc_180093202
0x1800931f7  mov     r8d, 85Ch
0x1800931fd  jmp     loc_1800932ED
0x180093202  xor     eax, eax
0x180093204  mov     [rdx], ax
0x180093207  lea     r15, [rdx+2]
0x18009320b  mov     [rsp+58h+dwType], eax
0x18009320f  sub     rdx, rbx
0x180093212  sar     rdx, 1; BufferCount
0x180093215  lea     r9, [rsp+58h+dwType]
0x18009321a  lea     r8, aU; "%u"
0x180093221  mov     rcx, rbx; Buffer
0x180093224  call    cs:__imp__snwscanf_s
0x18009322a  mov     rcx, r15; wchar_t *
0x18009322d  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180093232  mov     r14d, eax
0x180093235  shr     r14d, 1
0x180093238  mov     ecx, r14d; unsigned __int64
0x18009323b  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180093240  mov     rbx, rax
0x180093243  mov     [rsp+58h+arg_18], rax
0x180093248  xor     esi, esi
0x18009324a  test    r14d, r14d
0x18009324d  jz      short loc_180093283
0x18009324f  mov     dword ptr [rsp+58h+arg_0], 0
0x180093257  lea     r9, [rsp+58h+arg_0]
0x18009325c  lea     r8, a02x; "%02x"
0x180093263  mov     edx, 2; BufferCount
0x180093268  mov     rcx, r15; Buffer
0x18009326b  call    cs:__imp__snwscanf_s
0x180093271  mov     al, byte ptr [rsp+58h+arg_0]
0x180093275  mov     [rsi+rbx], al
0x180093278  inc     esi
0x18009327a  add     r15, 4
0x18009327e  cmp     esi, r14d
0x180093281  jb      short loc_18009324F
0x180093283  mov     [rsp+58h+cbData], r14d; cbData
0x180093288  mov     [rsp+58h+lpData], rbx; lpData
0x18009328d  mov     r9d, [rsp+58h+dwType]; dwType
0x180093292  xor     r8d, r8d; Reserved
0x180093295  mov     rdx, rdi; lpValueName
0x180093298  mov     rcx, rbp; hKey
0x18009329b  call    cs:__imp_RegSetValueExW
0x1800932a1  mov     edi, eax
0x1800932a3  test    eax, eax
0x1800932a5  jz      short loc_1800932D9
0x1800932a7  jle     short loc_1800932B2
0x1800932a9  movzx   edi, ax
0x1800932ac  or      edi, 80070000h
0x1800932b2  test    edi, edi
0x1800932b4  jns     short loc_1800932CB
0x1800932b6  mov     r8d, 870h; unsigned __int16
0x1800932bc  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800932c3  mov     ecx, edi; int
0x1800932c5  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800932ca  nop
0x1800932cb  mov     rcx, rbx; Block
0x1800932ce  call    cs:__imp_free
0x1800932d4  nop
0x1800932d5  mov     eax, edi
0x1800932d7  jmp     short loc_180093302
0x1800932d9  mov     rcx, rbx; Block
0x1800932dc  call    cs:__imp_free
0x1800932e2  nop
0x1800932e3  xor     eax, eax
0x1800932e5  jmp     short loc_180093302
0x1800932e7  mov     r8d, 834h; unsigned __int16
0x1800932ed  mov     ebx, 0C00E0006h
0x1800932f2  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800932f9  mov     ecx, ebx; int
0x1800932fb  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180093300  mov     eax, ebx
0x180093302  mov     rbx, [rsp+58h+arg_10]
0x180093307  add     rsp, 30h
0x18009330b  pop     r15
0x18009330d  pop     r14
0x18009330f  pop     rdi
0x180093310  pop     rsi
0x180093311  pop     rbp
0x180093312  retn
```
