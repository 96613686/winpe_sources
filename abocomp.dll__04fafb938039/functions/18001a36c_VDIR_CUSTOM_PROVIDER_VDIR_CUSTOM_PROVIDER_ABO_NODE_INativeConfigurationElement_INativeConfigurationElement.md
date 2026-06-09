# VDIR_CUSTOM_PROVIDER::VDIR_CUSTOM_PROVIDER(ABO_NODE *,INativeConfigurationElement *,INativeConfigurationElement *)

- ea: `0x18001a36c`
- end: `0x18001a43e`
- name: `??0VDIR_CUSTOM_PROVIDER@@QEAA@PEAVABO_NODE@@PEAVINativeConfigurationElement@@1@Z`
- size: `210`
- prototype: `VDIR_CUSTOM_PROVIDER *__fastcall(VDIR_CUSTOM_PROVIDER *__hidden this, struct ABO_NODE *, struct INativeConfigurationElement *, struct INativeConfigurationElement *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18001a860`
- `0x18001b158`

## callees

- `0x180001f90`
- `0x18001a36c`
- `0x18002c010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001a403`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001a403`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001a413`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001a413`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001a397`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001a397`

## pseudocode

```c
VDIR_CUSTOM_PROVIDER *__fastcall VDIR_CUSTOM_PROVIDER::VDIR_CUSTOM_PROVIDER(
        VDIR_CUSTOM_PROVIDER *this,
        struct ABO_NODE *a2,
        struct INativeConfigurationElement *a3,
        struct INativeConfigurationElement *a4)
{
  __int64 v7; // rax
  int v8; // ebx
  const unsigned __int16 *Str; // rax
  const unsigned __int16 *v11; // [rsp+60h] [rbp+8h] BYREF

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &VDIR_CUSTOM_PROVIDER::`vftable';
  *((_QWORD *)this + 2) = a2;
  STRU::STRU((VDIR_CUSTOM_PROVIDER *)((char *)this + 40));
  *((_QWORD *)this + 4) = a3;
  v7 = *(_QWORD *)a3;
  v11 = 0;
  (*(void (__fastcall **)(struct INativeConfigurationElement *))(v7 + 8))(a3);
  *((_QWORD *)this + 3) = a4;
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
      L"Failed to Get AppPoolName for Application associated with VDir node (%s).  error = %08x\n",
      Str,
      (unsigned int)v8);
  }
  else
  {
    STRU::Copy((VDIR_CUSTOM_PROVIDER *)((char *)this + 40), v11);
  }
  return this;
}

```

## disassembly

```asm
0x18001a36c  push    rbx
0x18001a36e  push    rbp
0x18001a36f  push    rsi
0x18001a370  push    rdi
0x18001a371  sub     rsp, 38h
0x18001a375  lea     rax, ??_7VDIR_CUSTOM_PROVIDER@@6B@; const VDIR_CUSTOM_PROVIDER::`vftable'
0x18001a37c  mov     dword ptr [rcx+8], 1
0x18001a383  mov     [rcx], rax
0x18001a386  mov     rsi, rcx
0x18001a389  mov     [rcx+10h], rdx
0x18001a38d  mov     rdi, r9
0x18001a390  add     rcx, 28h ; '('
0x18001a394  mov     rbx, r8
0x18001a397  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001a39d  mov     [rsi+20h], rbx
0x18001a3a1  mov     rcx, rbx
0x18001a3a4  mov     rax, [rbx]
0x18001a3a7  mov     [rsp+58h+arg_0], 0
0x18001a3b0  mov     rax, [rax+8]
0x18001a3b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3b9  mov     [rsi+18h], rdi
0x18001a3bd  mov     rcx, rdi
0x18001a3c0  mov     rax, [rdi]
0x18001a3c3  mov     rax, [rax+8]
0x18001a3c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3cc  mov     rcx, [rsi+18h]
0x18001a3d0  lea     r8, [rsp+58h+arg_0]
0x18001a3d5  xor     r9d, r9d
0x18001a3d8  mov     [rsp+58h+var_38], 0
0x18001a3e1  lea     rdx, aApplicationpoo_0; "applicationPool"
0x18001a3e8  mov     rax, [rcx]
0x18001a3eb  mov     rax, [rax+40h]
0x18001a3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3f4  mov     ebx, eax
0x18001a3f6  test    eax, eax
0x18001a3f8  js      short loc_18001A40B
0x18001a3fa  mov     rdx, [rsp+58h+arg_0]
0x18001a3ff  lea     rcx, [rsi+28h]
0x18001a403  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001a409  jmp     short loc_18001A432
0x18001a40b  mov     rcx, [rsi+10h]
0x18001a40f  add     rcx, 38h ; '8'
0x18001a413  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001a419  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18001a420  lea     rdx, aFailedToGetApp_0; "Failed to Get AppPoolName for Applicati"...
0x18001a427  mov     r8, rax
0x18001a42a  mov     r9d, ebx
0x18001a42d  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18001a432  mov     rax, rsi
0x18001a435  add     rsp, 38h
0x18001a439  pop     rdi
0x18001a43a  pop     rsi
0x18001a43b  pop     rbp
0x18001a43c  pop     rbx
0x18001a43d  retn
```
