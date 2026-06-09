# CbsTempDirectoryWorkerThreadProc(void *)

- ea: `0x14000e550`
- end: `0x14000e60a`
- name: `?CbsTempDirectoryWorkerThreadProc@@YAKPEAX@Z`
- size: `186`
- prototype: `__int64 __fastcall(PVOID Parameter, bool)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x140002310`
- `0x140006514`
- `0x14000e550`
- `0x14000e728`
- `0x14000ebe0`
- `0x1400240a4`
- `0x1400240f0`
- `0x140024bf4`

## pseudocode

```c
__int64 __fastcall CbsTempDirectoryWorkerThreadProc(PVOID Parameter, bool a2)
{
  int v3; // ebx
  wchar_t *v5; // [rsp+30h] [rbp-88h] BYREF
  void *v6; // [rsp+38h] [rbp-80h] BYREF
  __int16 v7; // [rsp+45h] [rbp-73h]
  char v8; // [rsp+47h] [rbp-71h]
  _BYTE v9[80]; // [rsp+50h] [rbp-68h] BYREF

  v5 = 0;
  AutoThreadPriority::AutoThreadPriority((AutoThreadPriority *)v9, a2);
  v6 = Parameter;
  v7 = 0;
  v8 = 0;
  if ( Parameter )
  {
    AutoThreadPriority::SetPriority(v9, 4294967294LL, 0);
    v3 = GetSystemTempCbsDeleteFolderPath((struct AutoScz *)&v5);
    if ( v3 >= 0 )
      v3 = DeleteFolder(&v6, v5);
  }
  else
  {
    v3 = -2147024809;
  }
  AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v9);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000e550  push    rbx
0x14000e552  sub     rsp, 0B0h
0x14000e559  mov     rax, cs:__security_cookie
0x14000e560  xor     rax, rsp
0x14000e563  mov     [rsp+0B8h+var_18], rax
0x14000e56b  mov     rbx, rcx
0x14000e56e  mov     [rsp+0B8h+var_88], 0
0x14000e577  lea     rcx, [rsp+0B8h+var_68]; this
0x14000e57c  call    ??0AutoThreadPriority@@QEAA@_N@Z; AutoThreadPriority::AutoThreadPriority(bool)
0x14000e581  xor     ecx, ecx
0x14000e583  mov     [rsp+0B8h+var_80], rbx
0x14000e588  xor     al, al
0x14000e58a  mov     [rsp+0B8h+var_73], cx
0x14000e58f  mov     [rsp+0B8h+var_71], cl
0x14000e593  test    rbx, rbx
0x14000e596  jnz     short loc_14000E59F
0x14000e598  mov     ebx, 80070057h
0x14000e59d  jmp     short loc_14000E5DB
0x14000e59f  mov     r9d, 1
0x14000e5a5  mov     [rsp+0B8h+var_98], al
0x14000e5a9  xor     r8d, r8d
0x14000e5ac  lea     rcx, [rsp+0B8h+var_68]
0x14000e5b1  lea     edx, [r9-3]
0x14000e5b5  call    ?SetPriority@AutoThreadPriority@@AEAAXHW4_IO_PRIORITY_HINT@@K_N@Z; AutoThreadPriority::SetPriority(int,_IO_PRIORITY_HINT,ulong,bool)
0x14000e5ba  lea     rcx, [rsp+0B8h+var_88]; struct AutoScz *
0x14000e5bf  call    ?GetSystemTempCbsDeleteFolderPath@@YAJAEAVAutoScz@@@Z; GetSystemTempCbsDeleteFolderPath(AutoScz &)
0x14000e5c4  mov     ebx, eax
0x14000e5c6  test    eax, eax
0x14000e5c8  js      short loc_14000E5DB
0x14000e5ca  mov     rdx, [rsp+0B8h+var_88]; wchar_t *
0x14000e5cf  lea     rcx, [rsp+0B8h+var_80]; void **
0x14000e5d4  call    ?DeleteFolder@@YAJPEAPEAXQEB_W@Z; DeleteFolder(void * *,wchar_t const * const)
0x14000e5d9  mov     ebx, eax
0x14000e5db  lea     rcx, [rsp+0B8h+var_68]; this
0x14000e5e0  call    ??1AutoThreadPriority@@QEAA@XZ; AutoThreadPriority::~AutoThreadPriority(void)
0x14000e5e5  lea     rcx, [rsp+0B8h+var_88]
0x14000e5ea  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000e5ef  mov     eax, ebx
0x14000e5f1  mov     rcx, [rsp+0B8h+var_18]
0x14000e5f9  xor     rcx, rsp; StackCookie
0x14000e5fc  call    __security_check_cookie
0x14000e601  add     rsp, 0B0h
0x14000e608  pop     rbx
0x14000e609  retn
```
