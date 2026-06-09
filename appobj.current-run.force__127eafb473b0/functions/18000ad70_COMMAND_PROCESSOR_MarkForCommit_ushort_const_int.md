# COMMAND_PROCESSOR::MarkForCommit(ushort const *,int)

- ea: `0x18000ad70`
- end: `0x18000aecb`
- name: `?MarkForCommit@COMMAND_PROCESSOR@@UEAAJPEBGH@Z`
- size: `347`
- prototype: `int(COMMAND_PROCESSOR *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001fb0`
- `0x180002e90`
- `0x1800049b0`
- `0x180006608`
- `0x18000ad70`
- `0x18000bd20`
- `0x180034cbe`
- `0x180034d00`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000ae48`
- `msvcrt!_wcsicmp` at `0x18000ae48`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::MarkForCommit(COMMAND_PROCESSOR *this, const unsigned __int8 *a2, int a3)
{
  int refreshed; // ebx
  wchar_t *v7; // r15
  __int64 v8; // rdx
  unsigned int i; // esi
  __int64 v10; // rdi
  _BYTE v12[32]; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t *String2; // [rsp+40h] [rbp-C0h]
  int v14; // [rsp+48h] [rbp-B8h]
  __int16 v15; // [rsp+4Ch] [rbp-B4h]
  unsigned int v16; // [rsp+50h] [rbp-B0h]
  __int16 v17; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[510]; // [rsp+62h] [rbp-9Eh] BYREF

  memset_0(v18, 0, sizeof(v18));
  v14 = 512;
  String2 = (wchar_t *)&v17;
  v15 = 256;
  v16 = 0;
  v17 = 0;
  refreshed = STRU::Copy((STRU *)v12, a2);
  if ( refreshed >= 0 )
  {
    while ( 1 )
    {
      v7 = String2;
      if ( v16 <= 1 )
        break;
      v8 = v16 - 1;
      if ( String2[v8] != 47 )
        break;
      if ( !STRU::SetLen((STRU *)v12, v8) )
      {
        refreshed = -2147024774;
        goto LABEL_15;
      }
    }
    for ( i = 0; i < *((_DWORD *)this + 80); ++i )
    {
      v10 = *(_QWORD *)(*((_QWORD *)this + 39) + 8LL * i);
      if ( !a2 || !_wcsicmp(*(const wchar_t **)(v10 + 48), v7) )
      {
        *(_DWORD *)(v10 + 188) = 1;
        if ( a3 )
        {
          refreshed = CONFIG_SYSTEM_ENTRY::Commit((CONFIG_SYSTEM_ENTRY *)v10);
          if ( refreshed < 0 )
            break;
          refreshed = CONFIG_SYSTEM_ENTRY::RefreshConfiguration((CONFIG_SYSTEM_ENTRY *)v10);
          if ( refreshed < 0 )
            break;
        }
        else
        {
          *((_DWORD *)this + 54) = 1;
        }
      }
    }
  }
LABEL_15:
  BUFFER::~BUFFER((BUFFER *)v12);
  return (unsigned int)refreshed;
}

```

## disassembly

```asm
0x18000ad70  mov     [rsp-8+arg_10], rbx
0x18000ad75  push    rbp
0x18000ad76  push    rsi
0x18000ad77  push    rdi
0x18000ad78  push    r12
0x18000ad7a  push    r13
0x18000ad7c  push    r14
0x18000ad7e  push    r15
0x18000ad80  lea     rbp, [rsp-170h]
0x18000ad88  sub     rsp, 270h
0x18000ad8f  mov     rax, cs:__security_cookie
0x18000ad96  xor     rax, rsp
0x18000ad99  mov     [rbp+1A0h+var_40], rax
0x18000ada0  mov     r13d, r8d
0x18000ada3  mov     r12, rdx
0x18000ada6  mov     r14, rcx
0x18000ada9  xor     edx, edx; Val
0x18000adab  mov     r8d, 1FEh; Size
0x18000adb1  lea     rcx, [rsp+2A0h+var_23E]; void *
0x18000adb6  call    memset_0
0x18000adbb  lea     rax, [rsp+2A0h+var_240]
0x18000adc0  mov     [rsp+2A0h+var_258], 200h
0x18000adc8  xor     edi, edi
0x18000adca  mov     [rsp+2A0h+String2], rax
0x18000adcf  mov     rdx, r12; unsigned __int16 *
0x18000add2  mov     [rsp+2A0h+var_254], 100h
0x18000add9  lea     rcx, [rsp+2A0h+var_280]; this
0x18000adde  mov     [rsp+2A0h+var_250], edi
0x18000ade2  mov     [rsp+2A0h+var_240], di
0x18000ade7  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000adec  mov     ebx, eax
0x18000adee  test    eax, eax
0x18000adf0  js      loc_18000AE95
0x18000adf6  mov     eax, [rsp+2A0h+var_250]
0x18000adfa  mov     r15, [rsp+2A0h+String2]
0x18000adff  cmp     eax, 1
0x18000ae02  jbe     short loc_18000AE24
0x18000ae04  lea     edx, [rax-1]; unsigned int
0x18000ae07  cmp     word ptr [r15+rdx*2], 2Fh ; '/'
0x18000ae0d  jnz     short loc_18000AE24
0x18000ae0f  lea     rcx, [rsp+2A0h+var_280]; this
0x18000ae14  call    ?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18000ae19  test    al, al
0x18000ae1b  jnz     short loc_18000ADF6
0x18000ae1d  mov     ebx, 8007007Ah
0x18000ae22  jmp     short loc_18000AE95
0x18000ae24  mov     esi, edi
0x18000ae26  cmp     [r14+140h], edi
0x18000ae2d  jbe     short loc_18000AE95
0x18000ae2f  mov     rax, [r14+138h]
0x18000ae36  mov     ecx, esi
0x18000ae38  mov     rdi, [rax+rcx*8]
0x18000ae3c  test    r12, r12
0x18000ae3f  jz      short loc_18000AE52
0x18000ae41  mov     rcx, [rdi+30h]; String1
0x18000ae45  mov     rdx, r15; String2
0x18000ae48  call    cs:__imp__wcsicmp
0x18000ae4e  test    eax, eax
0x18000ae50  jnz     short loc_18000AE8A
0x18000ae52  mov     dword ptr [rdi+0BCh], 1
0x18000ae5c  test    r13d, r13d
0x18000ae5f  jz      short loc_18000AE7F
0x18000ae61  mov     rcx, rdi; this
0x18000ae64  call    ?Commit@CONFIG_SYSTEM_ENTRY@@QEAAJXZ; CONFIG_SYSTEM_ENTRY::Commit(void)
0x18000ae69  mov     ebx, eax
0x18000ae6b  test    eax, eax
0x18000ae6d  js      short loc_18000AE95
0x18000ae6f  mov     rcx, rdi; this
0x18000ae72  call    ?RefreshConfiguration@CONFIG_SYSTEM_ENTRY@@QEAAJXZ; CONFIG_SYSTEM_ENTRY::RefreshConfiguration(void)
0x18000ae77  mov     ebx, eax
0x18000ae79  test    eax, eax
0x18000ae7b  js      short loc_18000AE95
0x18000ae7d  jmp     short loc_18000AE8A
0x18000ae7f  mov     dword ptr [r14+0D8h], 1
0x18000ae8a  inc     esi
0x18000ae8c  cmp     esi, [r14+140h]
0x18000ae93  jb      short loc_18000AE2F
0x18000ae95  lea     rcx, [rsp+2A0h+var_280]; this
0x18000ae9a  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000ae9f  mov     eax, ebx
0x18000aea1  mov     rcx, [rbp+1A0h+var_40]
0x18000aea8  xor     rcx, rsp; StackCookie
0x18000aeab  call    __security_check_cookie
0x18000aeb0  mov     rbx, [rsp+2A0h+arg_10]
0x18000aeb8  add     rsp, 270h
0x18000aebf  pop     r15
0x18000aec1  pop     r14
0x18000aec3  pop     r13
0x18000aec5  pop     r12
0x18000aec7  pop     rdi
0x18000aec8  pop     rsi
0x18000aec9  pop     rbp
0x18000aeca  retn
```
