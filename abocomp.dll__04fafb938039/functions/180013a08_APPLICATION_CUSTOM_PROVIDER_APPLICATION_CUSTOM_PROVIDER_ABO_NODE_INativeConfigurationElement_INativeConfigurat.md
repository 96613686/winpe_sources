# APPLICATION_CUSTOM_PROVIDER::APPLICATION_CUSTOM_PROVIDER(ABO_NODE *,INativeConfigurationElement *,INativeConfigurationElement *)

- ea: `0x180013a08`
- end: `0x180013ae2`
- name: `??0APPLICATION_CUSTOM_PROVIDER@@QEAA@PEAVABO_NODE@@PEAVINativeConfigurationElement@@1@Z`
- size: `218`
- prototype: `APPLICATION_CUSTOM_PROVIDER *__fastcall(APPLICATION_CUSTOM_PROVIDER *__hidden this, struct ABO_NODE *, struct INativeConfigurationElement *, struct INativeConfigurationElement *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180014488`
- `0x180016b1c`

## callees

- `0x180001f90`
- `0x180013a08`
- `0x18002c010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180013aa7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180013aa7`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180013ab7`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180013ab7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180013a33`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180013a33`

## pseudocode

```c
APPLICATION_CUSTOM_PROVIDER *__fastcall APPLICATION_CUSTOM_PROVIDER::APPLICATION_CUSTOM_PROVIDER(
        APPLICATION_CUSTOM_PROVIDER *this,
        struct ABO_NODE *a2,
        struct INativeConfigurationElement *a3,
        struct INativeConfigurationElement *a4)
{
  __int64 v7; // rax
  int v8; // ebx
  const unsigned __int16 *Str; // rax
  const unsigned __int16 *v11; // [rsp+60h] [rbp+8h] BYREF

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &APPLICATION_CUSTOM_PROVIDER::`vftable';
  *((_QWORD *)this + 2) = a2;
  STRU::STRU((APPLICATION_CUSTOM_PROVIDER *)((char *)this + 40));
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 3) = a3;
  v7 = *(_QWORD *)a3;
  v11 = 0;
  (*(void (__fastcall **)(struct INativeConfigurationElement *))(v7 + 8))(a3);
  *((_QWORD *)this + 4) = a4;
  (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)a4 + 8LL))(a4);
  v8 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(**((_QWORD **)this + 3) + 64LL))(
         *((_QWORD *)this + 3),
         L"applicationPool",
         &v11,
         0,
         0);
  if ( v8 < 0 )
  {
    Str = STRU::QueryStr((STRU *)(*((_QWORD *)this + 2) + 56LL));
    ABO_MAPPER_LOG::WriteLogEntry(
      (HANDLE *)g_pAboLog,
      L"Failed to Get AppPoolName for Application associated with node (%s).  error = %08x\n",
      Str,
      (unsigned int)v8);
  }
  else
  {
    STRU::Copy((APPLICATION_CUSTOM_PROVIDER *)((char *)this + 40), v11);
  }
  return this;
}

```

## disassembly

```asm
0x180013a08  push    rbx
0x180013a0a  push    rbp
0x180013a0b  push    rsi
0x180013a0c  push    rdi
0x180013a0d  sub     rsp, 38h
0x180013a11  lea     rax, ??_7APPLICATION_CUSTOM_PROVIDER@@6B@; const APPLICATION_CUSTOM_PROVIDER::`vftable'
0x180013a18  mov     dword ptr [rcx+8], 1
0x180013a1f  mov     [rcx], rax
0x180013a22  mov     rsi, rcx
0x180013a25  mov     [rcx+10h], rdx
0x180013a29  mov     rdi, r9
0x180013a2c  add     rcx, 28h ; '('
0x180013a30  mov     rbx, r8
0x180013a33  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180013a39  mov     qword ptr [rsi+60h], 0
0x180013a41  mov     rcx, rbx
0x180013a44  mov     [rsi+18h], rbx
0x180013a48  mov     rax, [rbx]
0x180013a4b  mov     [rsp+58h+arg_0], 0
0x180013a54  mov     rax, [rax+8]
0x180013a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a5d  mov     [rsi+20h], rdi
0x180013a61  mov     rcx, rdi
0x180013a64  mov     rax, [rdi]
0x180013a67  mov     rax, [rax+8]
0x180013a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a70  mov     rcx, [rsi+18h]
0x180013a74  lea     r8, [rsp+58h+arg_0]
0x180013a79  xor     r9d, r9d
0x180013a7c  mov     [rsp+58h+var_38], 0
0x180013a85  lea     rdx, aApplicationpoo_0; "applicationPool"
0x180013a8c  mov     rax, [rcx]
0x180013a8f  mov     rax, [rax+40h]
0x180013a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a98  mov     ebx, eax
0x180013a9a  test    eax, eax
0x180013a9c  js      short loc_180013AAF
0x180013a9e  mov     rdx, [rsp+58h+arg_0]
0x180013aa3  lea     rcx, [rsi+28h]
0x180013aa7  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180013aad  jmp     short loc_180013AD6
0x180013aaf  mov     rcx, [rsi+10h]
0x180013ab3  add     rcx, 38h ; '8'
0x180013ab7  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180013abd  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180013ac4  lea     rdx, aFailedToGetApp_1; "Failed to Get AppPoolName for Applicati"...
0x180013acb  mov     r8, rax
0x180013ace  mov     r9d, ebx
0x180013ad1  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180013ad6  mov     rax, rsi
0x180013ad9  add     rsp, 38h
0x180013add  pop     rdi
0x180013ade  pop     rsi
0x180013adf  pop     rbp
0x180013ae0  pop     rbx
0x180013ae1  retn
```
