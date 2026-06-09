# AddAllHosts(MOUNT_POINT_MAP *,WSTRING *,ARRAY *)

- ea: `0x180008e18`
- end: `0x180008fbe`
- name: `?AddAllHosts@@YAEPEAVMOUNT_POINT_MAP@@PEAVWSTRING@@PEAVARRAY@@@Z`
- size: `422`
- prototype: `unsigned __int8(struct MOUNT_POINT_MAP *, struct WSTRING *, struct ARRAY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x180008fc4`

## callees

- `0x180003bf0`
- `0x180008e18`
- `0x180009174`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008f75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008fa9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008f75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008fa9`
- `ulib!??0ARRAY@@QEAA@XZ` at `0x180008e3d`
- `ulib!??0ARRAY@@QEAA@XZ` at `0x180008e3d`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180008edf`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180008edf`
- `IfsUtil!?Initialize@DP_DRIVE@@QEAAEPEBVWSTRING@@PEAVMESSAGE@@EE@Z` at `0x180008f20`
- `IfsUtil!?Initialize@DP_DRIVE@@QEAAEPEBVWSTRING@@PEAVMESSAGE@@EE@Z` at `0x180008f20`
- `IfsUtil!??0DP_DRIVE@@QEAA@XZ` at `0x180008f01`
- `IfsUtil!??0DP_DRIVE@@QEAA@XZ` at `0x180008f01`
- `IfsUtil!?QueryID@DP_DRIVE@@QEAAEPEAVWSTRING@@PEBV2@E@Z` at `0x180008f4c`
- `IfsUtil!?QueryID@DP_DRIVE@@QEAAEPEAVWSTRING@@PEBV2@E@Z` at `0x180008f4c`

## pseudocode

```c
unsigned __int8 __fastcall AddAllHosts(struct MOUNT_POINT_MAP *a1, struct WSTRING *a2, struct ARRAY *a3)
{
  ARRAY *v5; // rax
  struct ARRAY *v6; // rbx
  __int64 v7; // rbx
  DWORD v8; // ecx
  const struct WSTRING *v9; // rbp
  DSTRING *v10; // rax
  struct WSTRING *v11; // rsi
  DP_DRIVE *v12; // rax
  DP_DRIVE *v13; // rax
  DP_DRIVE *v14; // rdi

  v5 = (ARRAY *)operator new(0x28u);
  if ( v5 )
    v6 = ARRAY::ARRAY(v5);
  else
    v6 = 0;
  if ( !a2 || !v6 )
  {
    v8 = 87;
    goto LABEL_23;
  }
  if ( FindHosts(a2, v6) )
  {
    if ( (*(unsigned int (__fastcall **)(struct ARRAY *))(*(_QWORD *)v6 + 32LL))(v6) )
    {
      v7 = (*(__int64 (__fastcall **)(struct ARRAY *))(*(_QWORD *)v6 + 48LL))(v6);
      if ( !v7 )
      {
        v8 = 8;
LABEL_23:
        SetLastError(v8);
        return 0;
      }
      while ( 1 )
      {
        v9 = (const struct WSTRING *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 40LL))(v7);
        if ( !v9 )
          break;
        v10 = (DSTRING *)operator new(0x30u);
        v11 = v10;
        if ( !v10
          || (DSTRING::DSTRING(v10),
              *(_QWORD *)v11 = &DSTRING::`local vftable',
              (v12 = (DP_DRIVE *)operator new(0x180u)) == 0)
          || (v13 = DP_DRIVE::DP_DRIVE(v12), (v14 = v13) == 0) )
        {
          SetLastError(8u);
          (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
          return 0;
        }
        if ( DP_DRIVE::Initialize(v13, v9, 0, 1u, 0) )
        {
          if ( DP_DRIVE::QueryID(v14, v11, 0, 0) )
            (*(void (__fastcall **)(struct ARRAY *, struct WSTRING *))(*(_QWORD *)a3 + 24LL))(a3, v11);
        }
        (**(void (__fastcall ***)(DP_DRIVE *, __int64))v14)(v14, 1);
      }
      (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
    }
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180008e18  push    rbx
0x180008e1a  push    rbp
0x180008e1b  push    rsi
0x180008e1c  push    rdi
0x180008e1d  push    r14
0x180008e1f  push    r15
0x180008e21  sub     rsp, 38h
0x180008e25  mov     ecx, 28h ; '('; unsigned __int64
0x180008e2a  mov     r14, r8
0x180008e2d  mov     rdi, rdx
0x180008e30  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008e35  test    rax, rax
0x180008e38  jz      short loc_180008E48
0x180008e3a  mov     rcx, rax
0x180008e3d  call    cs:__imp_??0ARRAY@@QEAA@XZ; ARRAY::ARRAY(void)
0x180008e43  mov     rbx, rax
0x180008e46  jmp     short loc_180008E4A
0x180008e48  xor     ebx, ebx
0x180008e4a  test    rdi, rdi
0x180008e4d  jz      loc_180008FA4
0x180008e53  test    rbx, rbx
0x180008e56  jz      loc_180008FA4
0x180008e5c  mov     rdx, rbx; struct ARRAY *
0x180008e5f  mov     rcx, rdi; struct WSTRING *
0x180008e62  call    ?FindHosts@@YAEPEAVWSTRING@@PEAVARRAY@@@Z; FindHosts(WSTRING *,ARRAY *)
0x180008e67  test    al, al
0x180008e69  jz      loc_180008FAF
0x180008e6f  mov     rax, [rbx]
0x180008e72  mov     rcx, rbx
0x180008e75  mov     rax, [rax+20h]
0x180008e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e7e  mov     r15d, 1
0x180008e84  test    eax, eax
0x180008e86  jz      loc_180008F9F
0x180008e8c  mov     rax, [rbx]
0x180008e8f  mov     rcx, rbx
0x180008e92  mov     rax, [rax+30h]
0x180008e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e9b  mov     rbx, rax
0x180008e9e  test    rax, rax
0x180008ea1  jnz     short loc_180008EAB
0x180008ea3  lea     ecx, [rax+8]
0x180008ea6  jmp     loc_180008FA9
0x180008eab  mov     rax, [rbx]
0x180008eae  mov     rcx, rbx
0x180008eb1  mov     rax, [rax+28h]
0x180008eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eba  mov     rbp, rax
0x180008ebd  test    rax, rax
0x180008ec0  jz      loc_180008F8E
0x180008ec6  mov     ecx, 30h ; '0'; unsigned __int64
0x180008ecb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008ed0  mov     rsi, rax
0x180008ed3  test    rax, rax
0x180008ed6  jz      loc_180008F70
0x180008edc  mov     rcx, rax
0x180008edf  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x180008ee5  lea     rax, ??_SDSTRING@@6B@; const DSTRING::`local vftable'
0x180008eec  mov     ecx, 180h; unsigned __int64
0x180008ef1  mov     [rsi], rax
0x180008ef4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008ef9  test    rax, rax
0x180008efc  jz      short loc_180008F70
0x180008efe  mov     rcx, rax
0x180008f01  call    cs:__imp_??0DP_DRIVE@@QEAA@XZ; DP_DRIVE::DP_DRIVE(void)
0x180008f07  mov     rdi, rax
0x180008f0a  test    rax, rax
0x180008f0d  jz      short loc_180008F70
0x180008f0f  mov     r9b, r15b
0x180008f12  mov     [rsp+68h+var_48], 0
0x180008f17  xor     r8d, r8d
0x180008f1a  mov     rdx, rbp
0x180008f1d  mov     rcx, rax
0x180008f20  call    cs:__imp_?Initialize@DP_DRIVE@@QEAAEPEBVWSTRING@@PEAVMESSAGE@@EE@Z; DP_DRIVE::Initialize(WSTRING const *,MESSAGE *,uchar,uchar)
0x180008f26  test    al, al
0x180008f28  jnz     short loc_180008F40
0x180008f2a  mov     rcx, [rdi]
0x180008f2d  mov     rax, [rcx]
0x180008f30  mov     rcx, rdi
0x180008f33  mov     edx, r15d
0x180008f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f3b  jmp     loc_180008EAB
0x180008f40  xor     r9d, r9d
0x180008f43  xor     r8d, r8d
0x180008f46  mov     rdx, rsi
0x180008f49  mov     rcx, rdi
0x180008f4c  call    cs:__imp_?QueryID@DP_DRIVE@@QEAAEPEAVWSTRING@@PEBV2@E@Z; DP_DRIVE::QueryID(WSTRING *,WSTRING const *,uchar)
0x180008f52  test    al, al
0x180008f54  jz      short loc_180008F68
0x180008f56  mov     rax, [r14]
0x180008f59  mov     rdx, rsi
0x180008f5c  mov     rcx, r14
0x180008f5f  mov     rax, [rax+18h]
0x180008f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f68  mov     rax, [rdi]
0x180008f6b  mov     rax, [rax]
0x180008f6e  jmp     short loc_180008F30
0x180008f70  mov     ecx, 8; dwErrCode
0x180008f75  call    cs:__imp_SetLastError
0x180008f7b  mov     rax, [rbx]
0x180008f7e  mov     edx, r15d
0x180008f81  mov     rcx, rbx
0x180008f84  mov     rax, [rax]
0x180008f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f8c  jmp     short loc_180008FAF
0x180008f8e  mov     rax, [rbx]
0x180008f91  mov     edx, r15d
0x180008f94  mov     rcx, rbx
0x180008f97  mov     rax, [rax]
0x180008f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f9f  mov     al, r15b
0x180008fa2  jmp     short loc_180008FB1
0x180008fa4  mov     ecx, 57h ; 'W'; dwErrCode
0x180008fa9  call    cs:__imp_SetLastError
0x180008faf  xor     al, al
0x180008fb1  add     rsp, 38h
0x180008fb5  pop     r15
0x180008fb7  pop     r14
0x180008fb9  pop     rdi
0x180008fba  pop     rsi
0x180008fbb  pop     rbp
0x180008fbc  pop     rbx
0x180008fbd  retn
```
