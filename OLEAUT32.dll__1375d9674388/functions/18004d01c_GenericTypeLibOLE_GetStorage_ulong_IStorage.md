# GenericTypeLibOLE::GetStorage(ulong,IStorage * *)

- ea: `0x18004d01c`
- end: `0x18004d1f3`
- name: `?GetStorage@GenericTypeLibOLE@@QEAAJKPEAPEAUIStorage@@@Z`
- size: `471`
- prototype: `__int64 __fastcall(GenericTypeLibOLE *__hidden this, unsigned int, struct IStorage **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800535c0`
- `0x180054d10`

## callees

- `0x180031e20`
- `0x18004d01c`
- `0x18004d900`
- `0x18004e87c`
- `0x180053754`
- `0x18005a29c`
- `0x18005a59c`
- `0x18009a618`
- `0x18009c010`

## import_xrefs

- `ext-ms-win-ole32-oleautomation-l1-1-0!ReadStorageProperties` at `0x18004d145`
- `ext-ms-win-ole32-oleautomation-l1-1-0!ReadStorageProperties` at `0x18004d1ac`
- `ext-ms-win-ole32-oleautomation-l1-1-0!ReadStorageProperties` at `0x18004d145`
- `ext-ms-win-ole32-oleautomation-l1-1-0!ReadStorageProperties` at `0x18004d1ac`

## pseudocode

```c
__int64 __fastcall GenericTypeLibOLE::GetStorage(GenericTypeLibOLE *this, unsigned int a2, struct IStorage **a3)
{
  unsigned __int16 *v6; // rax
  __int16 v7; // dx
  int v8; // edi
  struct ILockBytes *v9; // rbx
  struct IStorage *v10; // rbx
  struct ILockBytes *v11; // rbx
  char TypeLibPresent; // al
  struct ILockBytes *v14; // [rsp+40h] [rbp-30h] BYREF
  struct IStorage *v15; // [rsp+48h] [rbp-28h] BYREF
  struct IStorage *v16; // [rsp+50h] [rbp-20h] BYREF
  __int128 Buf1; // [rsp+58h] [rbp-18h] BYREF

  ++*((_DWORD *)this + 26);
  Buf1 = 0;
  v15 = 0;
  v16 = 0;
  v14 = 0;
  v6 = GenericTypeLibOLE::QszLibIdOrFile(this);
  if ( (v7 & 0x1000) == 0 )
  {
    v8 = OpenFileLockBytes(0, v6, &v14);
    if ( !v8 )
    {
      v11 = v14;
      v8 = GTLibStorage::OpenForReadOnly(v14, &v15);
      ((void (__fastcall *)(struct ILockBytes *))v11->lpVtbl->Release)(v11);
      if ( !v8 )
      {
        TypeLibPresent = IsMonikerLoadTypeLibPresent();
        v10 = v15;
        if ( TypeLibPresent )
        {
          v8 = ReadStorageProperties(v15, &Buf1);
          if ( !v8 )
          {
            if ( !memcmp_0(&Buf1, &CLSID_GenericTypeLibOLE, 0x10u) )
              goto LABEL_17;
            v8 = ((__int64 (__fastcall *)(struct IStorage *, __int64 *, _QWORD, _QWORD, _QWORD, int, struct IStorage **))v10->lpVtbl->OpenStorage)(
                   v10,
                   qword_1800B1248,
                   0,
                   a2,
                   0,
                   v8,
                   &v16);
            if ( !v8 )
            {
              v8 = ReadStorageProperties(v10, &Buf1);
              if ( !v8 )
              {
                *((_QWORD *)this + 19) = v10;
                v10 = v16;
                goto LABEL_17;
              }
              ((void (__fastcall *)(struct IStorage *))v16->lpVtbl->Release)(v16);
            }
          }
        }
        else
        {
          v8 = -2147467263;
        }
        ((void (__fastcall *)(struct IStorage *))v10->lpVtbl->Release)(v10);
      }
    }
LABEL_10:
    --*((_DWORD *)this + 26);
    return (unsigned int)v8;
  }
  v8 = OpenFileLockBytes(1, v6, &v14);
  if ( v8 < 0 )
    goto LABEL_10;
  v9 = v14;
  v8 = GTLibStorage::Create(v14, (unsigned int)*((unsigned __int16 *)this + 120) + 2, &v15);
  ((void (__fastcall *)(struct ILockBytes *))v9->lpVtbl->Release)(v9);
  if ( v8 )
    goto LABEL_10;
  v10 = v15;
LABEL_17:
  --*((_DWORD *)this + 26);
  if ( a3 )
    *a3 = v10;
  else
    *((_QWORD *)this + 18) = v10;
  return 0;
}

```

## disassembly

```asm
0x18004d01c  mov     [rsp-28h+arg_18], rbx
0x18004d021  push    rbp
0x18004d022  push    rsi
0x18004d023  push    rdi
0x18004d024  push    r14
0x18004d026  push    r15
0x18004d028  mov     rbp, rsp
0x18004d02b  sub     rsp, 70h
0x18004d02f  mov     rax, cs:__security_cookie
0x18004d036  xor     rax, rsp
0x18004d039  mov     [rbp+var_8], rax
0x18004d03d  inc     dword ptr [rcx+68h]
0x18004d040  xorps   xmm0, xmm0
0x18004d043  movups  [rbp+Buf1], xmm0
0x18004d047  mov     r14, r8
0x18004d04a  mov     [rbp+var_28], 0
0x18004d052  mov     r15d, edx
0x18004d055  mov     [rbp+var_20], 0
0x18004d05d  mov     rsi, rcx
0x18004d060  mov     [rbp+var_30], 0
0x18004d068  call    ?QszLibIdOrFile@GenericTypeLibOLE@@IEAAPEAGXZ; GenericTypeLibOLE::QszLibIdOrFile(void)
0x18004d06d  bt      edx, 0Ch
0x18004d071  lea     r8, [rbp+var_30]; struct ILockBytes **
0x18004d075  mov     rdx, rax; unsigned __int16 *
0x18004d078  jnb     short loc_18004D0C6
0x18004d07a  mov     ecx, 1; int
0x18004d07f  call    ?OpenFileLockBytes@@YAJHPEAGPEAPEAUILockBytes@@@Z; OpenFileLockBytes(int,ushort *,ILockBytes * *)
0x18004d084  mov     edi, eax
0x18004d086  test    eax, eax
0x18004d088  js      loc_18004D119
0x18004d08e  movzx   edx, word ptr [rsi+0F0h]
0x18004d095  lea     r8, [rbp+var_28]; struct IStorage **
0x18004d099  mov     rbx, [rbp+var_30]
0x18004d09d  add     edx, 2; unsigned int
0x18004d0a0  mov     rcx, rbx; struct ILockBytes *
0x18004d0a3  call    ?Create@GTLibStorage@@SAJPEAUILockBytes@@IPEAPEAUIStorage@@@Z; GTLibStorage::Create(ILockBytes *,uint,IStorage * *)
0x18004d0a8  mov     edi, eax
0x18004d0aa  mov     rcx, rbx
0x18004d0ad  mov     rax, [rbx]
0x18004d0b0  mov     rax, [rax+10h]
0x18004d0b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0b9  test    edi, edi
0x18004d0bb  jnz     short loc_18004D119
0x18004d0bd  mov     rbx, [rbp+var_28]
0x18004d0c1  jmp     loc_18004D1D8
0x18004d0c6  xor     ecx, ecx; int
0x18004d0c8  call    ?OpenFileLockBytes@@YAJHPEAGPEAPEAUILockBytes@@@Z; OpenFileLockBytes(int,ushort *,ILockBytes * *)
0x18004d0cd  mov     edi, eax
0x18004d0cf  test    eax, eax
0x18004d0d1  jnz     short loc_18004D119
0x18004d0d3  mov     rbx, [rbp+var_30]
0x18004d0d7  lea     rdx, [rbp+var_28]; struct IStorage **
0x18004d0db  mov     rcx, rbx; struct ILockBytes *
0x18004d0de  call    ?OpenForReadOnly@GTLibStorage@@SAJPEAUILockBytes@@PEAPEAUIStorage@@@Z; GTLibStorage::OpenForReadOnly(ILockBytes *,IStorage * *)
0x18004d0e3  mov     edi, eax
0x18004d0e5  mov     rcx, rbx
0x18004d0e8  mov     rax, [rbx]
0x18004d0eb  mov     rax, [rax+10h]
0x18004d0ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0f4  test    edi, edi
0x18004d0f6  jnz     short loc_18004D119
0x18004d0f8  call    IsMonikerLoadTypeLibPresent
0x18004d0fd  mov     rbx, [rbp+var_28]
0x18004d101  test    al, al
0x18004d103  jnz     short loc_18004D13E
0x18004d105  mov     edi, 80004001h
0x18004d10a  mov     rax, [rbx]
0x18004d10d  mov     rcx, rbx
0x18004d110  mov     rax, [rax+10h]
0x18004d114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d119  dec     dword ptr [rsi+68h]
0x18004d11c  mov     eax, edi
0x18004d11e  mov     rcx, [rbp+var_8]
0x18004d122  xor     rcx, rsp; StackCookie
0x18004d125  call    __security_check_cookie
0x18004d12a  mov     rbx, [rsp+70h+arg_18]
0x18004d132  add     rsp, 70h
0x18004d136  pop     r15
0x18004d138  pop     r14
0x18004d13a  pop     rdi
0x18004d13b  pop     rsi
0x18004d13c  pop     rbp
0x18004d13d  retn
0x18004d13e  lea     rdx, [rbp+Buf1]
0x18004d142  mov     rcx, rbx
0x18004d145  call    cs:__imp_ReadStorageProperties
0x18004d14b  mov     edi, eax
0x18004d14d  test    eax, eax
0x18004d14f  jnz     short loc_18004D10A
0x18004d151  lea     r8d, [rax+10h]; Size
0x18004d155  lea     rdx, CLSID_GenericTypeLibOLE; Buf2
0x18004d15c  lea     rcx, [rbp+Buf1]; Buf1
0x18004d160  call    memcmp_0
0x18004d165  test    eax, eax
0x18004d167  jz      short loc_18004D1D8
0x18004d169  mov     rax, [rbx]
0x18004d16c  lea     rcx, [rbp+var_20]
0x18004d170  mov     [rsp+70h+var_40], rcx
0x18004d175  lea     rdx, qword_1800B1248
0x18004d17c  mov     [rsp+70h+var_48], edi
0x18004d180  mov     r9d, r15d
0x18004d183  xor     r8d, r8d
0x18004d186  mov     [rsp+70h+var_50], 0
0x18004d18f  mov     rax, [rax+30h]
0x18004d193  mov     rcx, rbx
0x18004d196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d19b  mov     edi, eax
0x18004d19d  test    eax, eax
0x18004d19f  jnz     loc_18004D10A
0x18004d1a5  lea     rdx, [rbp+Buf1]
0x18004d1a9  mov     rcx, rbx
0x18004d1ac  call    cs:__imp_ReadStorageProperties
0x18004d1b2  mov     edi, eax
0x18004d1b4  test    eax, eax
0x18004d1b6  jz      short loc_18004D1CD
0x18004d1b8  mov     rcx, [rbp+var_20]
0x18004d1bc  mov     rax, [rcx]
0x18004d1bf  mov     rax, [rax+10h]
0x18004d1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d1c8  jmp     loc_18004D10A
0x18004d1cd  mov     [rsi+98h], rbx
0x18004d1d4  mov     rbx, [rbp+var_20]
0x18004d1d8  dec     dword ptr [rsi+68h]
0x18004d1db  test    r14, r14
0x18004d1de  jnz     short loc_18004D1E9
0x18004d1e0  mov     [rsi+90h], rbx
0x18004d1e7  jmp     short loc_18004D1EC
0x18004d1e9  mov     [r14], rbx
0x18004d1ec  xor     eax, eax
0x18004d1ee  jmp     loc_18004D11E
```
