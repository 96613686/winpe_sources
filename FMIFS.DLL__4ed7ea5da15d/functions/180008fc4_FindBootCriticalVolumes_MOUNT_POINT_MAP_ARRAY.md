# FindBootCriticalVolumes(MOUNT_POINT_MAP *,ARRAY *)

- ea: `0x180008fc4`
- end: `0x18000916b`
- name: `?FindBootCriticalVolumes@@YAEPEAVMOUNT_POINT_MAP@@PEAVARRAY@@@Z`
- size: `423`
- prototype: `unsigned __int8(struct MOUNT_POINT_MAP *, struct ARRAY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x1800015d0`

## callees

- `0x180003bf0`
- `0x180008e18`
- `0x180008fc4`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ff9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009139`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ff9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009139`
- `ulib!?Strcat@WSTRING@@QEAAEPEBG@Z` at `0x180009115`
- `ulib!?Strcat@WSTRING@@QEAAEPEBG@Z` at `0x180009115`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180008fdf`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180008fea`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180009072`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180008fdf`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180008fea`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180009072`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180009004`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000900f`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180009147`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180009152`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180009004`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000900f`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180009147`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180009152`
- `IfsUtil!?QueryID@DP_DRIVE@@QEAAEPEAVWSTRING@@PEBV2@E@Z` at `0x1800090ed`
- `IfsUtil!?QueryID@DP_DRIVE@@QEAAEPEAVWSTRING@@PEBV2@E@Z` at `0x1800090ed`
- `IfsUtil!?IsBootCriticalVolume@DP_DRIVE@@QEAAEXZ` at `0x1800090d7`
- `IfsUtil!?IsBootCriticalVolume@DP_DRIVE@@QEAAEXZ` at `0x1800090d7`
- `IfsUtil!??0LOG_IO_DP_DRIVE@@QEAA@XZ` at `0x180009050`
- `IfsUtil!??0LOG_IO_DP_DRIVE@@QEAA@XZ` at `0x180009050`
- `IfsUtil!?Initialize@LOG_IO_DP_DRIVE@@QEAAEPEBVWSTRING@@PEAVMESSAGE@@E@Z` at `0x1800090a8`
- `IfsUtil!?Initialize@LOG_IO_DP_DRIVE@@QEAAEPEBVWSTRING@@PEAVMESSAGE@@E@Z` at `0x1800090a8`
- `IfsUtil!?GetAt@MOUNT_POINT_MAP@@QEAAEKPEAVWSTRING@@0@Z` at `0x180009030`
- `IfsUtil!?GetAt@MOUNT_POINT_MAP@@QEAAEKPEAVWSTRING@@0@Z` at `0x180009030`

## pseudocode

```c
char __fastcall FindBootCriticalVolumes(struct MOUNT_POINT_MAP *a1, struct ARRAY *a2)
{
  unsigned int v5; // ebp
  char v6; // si
  LOG_IO_DP_DRIVE *v7; // rax
  DP_DRIVE *v8; // rdi
  DSTRING *v9; // rax
  struct WSTRING *v10; // rbx
  void (__fastcall **v11)(DP_DRIVE *, __int64); // rax
  DP_DRIVE *v12; // rcx
  struct MOUNT_POINT_MAP *v13; // rcx
  _BYTE v14[48]; // [rsp+20h] [rbp-98h] BYREF
  _BYTE v15[104]; // [rsp+50h] [rbp-68h] BYREF

  DSTRING::DSTRING((DSTRING *)v15);
  DSTRING::DSTRING((DSTRING *)v14);
  if ( a2 )
  {
    v5 = 0;
    v6 = 1;
    while ( MOUNT_POINT_MAP::GetAt(a1, v5, (struct WSTRING *)v15, (struct WSTRING *)v14) )
    {
      v7 = (LOG_IO_DP_DRIVE *)operator new(0x1E0u);
      if ( v7 )
        v8 = LOG_IO_DP_DRIVE::LOG_IO_DP_DRIVE(v7);
      else
        v8 = 0;
      v9 = (DSTRING *)operator new(0x30u);
      v10 = v9;
      if ( v9 )
      {
        DSTRING::DSTRING(v9);
        *(_QWORD *)v10 = &DSTRING::`local vftable';
      }
      else
      {
        v10 = 0;
      }
      if ( !v8 || !v10 )
      {
        SetLastError(8u);
        v6 = 0;
        break;
      }
      ++v5;
      if ( LOG_IO_DP_DRIVE::Initialize(v8, (const struct WSTRING *)v14, 0, 0) )
      {
        if ( DP_DRIVE::IsBootCriticalVolume(v8) )
        {
          if ( DP_DRIVE::QueryID(v8, v10, 0, 0) )
            (*(void (__fastcall **)(struct ARRAY *, struct WSTRING *))(*(_QWORD *)a2 + 24LL))(a2, v10);
          if ( WSTRING::Strcat((WSTRING *)v14, L"\\") )
            AddAllHosts(v13, (struct WSTRING *)v14, a2);
        }
        v11 = *(void (__fastcall ***)(DP_DRIVE *, __int64))v8;
        v12 = v8;
      }
      else
      {
        (**(void (__fastcall ***)(DP_DRIVE *, __int64))v8)(v8, 1);
        v11 = *(void (__fastcall ***)(DP_DRIVE *, __int64))v10;
        v12 = v10;
      }
      (*v11)(v12, 1);
    }
    DSTRING::~DSTRING((DSTRING *)v14);
    DSTRING::~DSTRING((DSTRING *)v15);
    return v6;
  }
  else
  {
    SetLastError(0x57u);
    DSTRING::~DSTRING((DSTRING *)v14);
    DSTRING::~DSTRING((DSTRING *)v15);
    return 0;
  }
}

```

## disassembly

```asm
0x180008fc4  push    rbx
0x180008fc6  push    rbp
0x180008fc7  push    rsi
0x180008fc8  push    rdi
0x180008fc9  push    r14
0x180008fcb  push    r15
0x180008fcd  sub     rsp, 88h
0x180008fd4  mov     r15, rcx
0x180008fd7  mov     r14, rdx
0x180008fda  lea     rcx, [rsp+0B8h+var_68]
0x180008fdf  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x180008fe5  lea     rcx, [rsp+0B8h+var_98]
0x180008fea  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x180008ff0  test    r14, r14
0x180008ff3  jnz     short loc_18000901C
0x180008ff5  lea     ecx, [r14+57h]; dwErrCode
0x180008ff9  call    cs:__imp_SetLastError
0x180008fff  lea     rcx, [rsp+0B8h+var_98]
0x180009004  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x18000900a  lea     rcx, [rsp+0B8h+var_68]
0x18000900f  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180009015  xor     al, al
0x180009017  jmp     loc_18000915B
0x18000901c  xor     ebp, ebp
0x18000901e  lea     esi, [rbp+1]
0x180009021  lea     r9, [rsp+0B8h+var_98]
0x180009026  mov     edx, ebp
0x180009028  lea     r8, [rsp+0B8h+var_68]
0x18000902d  mov     rcx, r15
0x180009030  call    cs:__imp_?GetAt@MOUNT_POINT_MAP@@QEAAEKPEAVWSTRING@@0@Z; MOUNT_POINT_MAP::GetAt(ulong,WSTRING *,WSTRING *)
0x180009036  test    al, al
0x180009038  jz      loc_180009142
0x18000903e  mov     ecx, 1E0h; unsigned __int64
0x180009043  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009048  test    rax, rax
0x18000904b  jz      short loc_18000905B
0x18000904d  mov     rcx, rax
0x180009050  call    cs:__imp_??0LOG_IO_DP_DRIVE@@QEAA@XZ; LOG_IO_DP_DRIVE::LOG_IO_DP_DRIVE(void)
0x180009056  mov     rdi, rax
0x180009059  jmp     short loc_18000905D
0x18000905b  xor     edi, edi
0x18000905d  mov     ecx, 30h ; '0'; unsigned __int64
0x180009062  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009067  mov     rbx, rax
0x18000906a  test    rax, rax
0x18000906d  jz      short loc_180009084
0x18000906f  mov     rcx, rax
0x180009072  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x180009078  lea     rax, ??_SDSTRING@@6B@; const DSTRING::`local vftable'
0x18000907f  mov     [rbx], rax
0x180009082  jmp     short loc_180009086
0x180009084  xor     ebx, ebx
0x180009086  test    rdi, rdi
0x180009089  jz      loc_180009134
0x18000908f  test    rbx, rbx
0x180009092  jz      loc_180009134
0x180009098  xor     r9d, r9d
0x18000909b  lea     rdx, [rsp+0B8h+var_98]
0x1800090a0  xor     r8d, r8d
0x1800090a3  mov     rcx, rdi
0x1800090a6  add     ebp, esi
0x1800090a8  call    cs:__imp_?Initialize@LOG_IO_DP_DRIVE@@QEAAEPEBVWSTRING@@PEAVMESSAGE@@E@Z; LOG_IO_DP_DRIVE::Initialize(WSTRING const *,MESSAGE *,uchar)
0x1800090ae  mov     rcx, rdi
0x1800090b1  test    al, al
0x1800090b3  jnz     short loc_1800090D7
0x1800090b5  mov     rax, [rdi]
0x1800090b8  mov     edx, esi
0x1800090ba  mov     rax, [rax]
0x1800090bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090c2  mov     rax, [rbx]
0x1800090c5  mov     rcx, rbx
0x1800090c8  mov     rax, [rax]
0x1800090cb  mov     edx, esi
0x1800090cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090d2  jmp     loc_180009021
0x1800090d7  call    cs:__imp_?IsBootCriticalVolume@DP_DRIVE@@QEAAEXZ; DP_DRIVE::IsBootCriticalVolume(void)
0x1800090dd  test    al, al
0x1800090df  jz      short loc_18000912C
0x1800090e1  xor     r9d, r9d
0x1800090e4  xor     r8d, r8d
0x1800090e7  mov     rdx, rbx
0x1800090ea  mov     rcx, rdi
0x1800090ed  call    cs:__imp_?QueryID@DP_DRIVE@@QEAAEPEAVWSTRING@@PEBV2@E@Z; DP_DRIVE::QueryID(WSTRING *,WSTRING const *,uchar)
0x1800090f3  test    al, al
0x1800090f5  jz      short loc_180009109
0x1800090f7  mov     rax, [r14]
0x1800090fa  mov     rdx, rbx
0x1800090fd  mov     rcx, r14
0x180009100  mov     rax, [rax+18h]
0x180009104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009109  lea     rdx, asc_18000BB4C; "\\"
0x180009110  lea     rcx, [rsp+0B8h+var_98]
0x180009115  call    cs:__imp_?Strcat@WSTRING@@QEAAEPEBG@Z; WSTRING::Strcat(ushort const *)
0x18000911b  test    al, al
0x18000911d  jz      short loc_18000912C
0x18000911f  mov     r8, r14; struct ARRAY *
0x180009122  lea     rdx, [rsp+0B8h+var_98]; struct WSTRING *
0x180009127  call    ?AddAllHosts@@YAEPEAVMOUNT_POINT_MAP@@PEAVWSTRING@@PEAVARRAY@@@Z; AddAllHosts(MOUNT_POINT_MAP *,WSTRING *,ARRAY *)
0x18000912c  mov     rax, [rdi]
0x18000912f  mov     rcx, rdi
0x180009132  jmp     short loc_1800090C8
0x180009134  mov     ecx, 8; dwErrCode
0x180009139  call    cs:__imp_SetLastError
0x18000913f  xor     sil, sil
0x180009142  lea     rcx, [rsp+0B8h+var_98]
0x180009147  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x18000914d  lea     rcx, [rsp+0B8h+var_68]
0x180009152  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180009158  mov     al, sil
0x18000915b  add     rsp, 88h
0x180009162  pop     r15
0x180009164  pop     r14
0x180009166  pop     rdi
0x180009167  pop     rsi
0x180009168  pop     rbp
0x180009169  pop     rbx
0x18000916a  retn
```
