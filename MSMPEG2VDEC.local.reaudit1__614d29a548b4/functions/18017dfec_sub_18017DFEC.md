# sub_18017DFEC

- ea: `0x18017dfec`
- end: `0x18017e19f`
- name: `sub_18017DFEC`
- size: `435`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18017e2b0`

## callees

- `0x1800dfdcc`
- `0x1800e3280`
- `0x1800ef9d0`
- `0x1800efcd0`
- `0x18017dfec`
- `0x18017e1d0`
- `0x18017ed80`
- `0x18017eea0`
- `0x180181410`
- `0x1801838e8`
- `0x180199120`
- `0x1801f23e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18017e030`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18017e030`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18017e05b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18017e05b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18017e0fe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18017e0fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017e111`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017e124`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017e111`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017e124`

## pseudocode

```c
__int64 __fastcall sub_18017DFEC(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx

  *(_QWORD *)a1 = &off_180207178;
  *(_QWORD *)(a1 + 1288) = off_180207158;
  *(_QWORD *)(a1 + 84) = 0;
  sub_18017ED80();
  sub_180181410(a1);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1800));
  if ( *(_QWORD *)(a1 + 1488) )
    sub_18017E1D0();
  *(_QWORD *)(a1 + 1488) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1800));
  v2 = *(_QWORD *)(a1 + 72);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *(_QWORD *)(a1 + 72) = 0;
  }
  v3 = *(_QWORD *)(a1 + 3216);
  if ( v3 )
  {
    if ( *(_QWORD *)(v3 + 4552) )
      sub_1800DFDCC();
    sub_1800E3280(*(_QWORD *)(a1 + 3216));
    sub_1800EFCD0(*(_QWORD *)(a1 + 3216));
    v4 = *(_QWORD *)(a1 + 2032);
    if ( v4 )
    {
      sub_180199120(v4 + 8);
      *(_QWORD *)(a1 + 2032) = 0;
    }
    v5 = *(_QWORD *)(a1 + 3216);
    if ( v5 )
      sub_1800EF9D0(v5, 1);
    *(_QWORD *)(a1 + 3216) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 1800));
  CloseHandle(*(HANDLE *)(a1 + 2040));
  CloseHandle(*(HANDLE *)(a1 + 2048));
  if ( *(_QWORD *)(a1 + 1520) )
  {
    v6 = *(_QWORD *)(a1 + 1480);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 40LL))(v6);
  }
  v7 = *(_QWORD *)(a1 + 1480);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *(_QWORD *)(a1 + 1480) = 0;
  }
  sub_18017EEA0(a1, 1);
  _InterlockedDecrement(&dword_180245FC4);
  return sub_1801838E8(a1);
}

```

## disassembly

```asm
0x18017dfec  mov     [rsp+arg_0], rbx
0x18017dff1  push    rdi
0x18017dff2  sub     rsp, 20h
0x18017dff6  mov     rbx, rcx
0x18017dff9  lea     rax, off_180207178
0x18017e000  mov     [rcx], rax
0x18017e003  lea     rax, off_180207158
0x18017e00a  mov     [rcx+508h], rax
0x18017e011  mov     qword ptr [rcx+54h], 0
0x18017e019  call    sub_18017ED80
0x18017e01e  mov     rcx, rbx
0x18017e021  call    sub_180181410
0x18017e026  lea     rdi, [rbx+708h]
0x18017e02d  mov     rcx, rdi; lpCriticalSection
0x18017e030  call    cs:EnterCriticalSection
0x18017e037  nop     dword ptr [rax+rax+00h]
0x18017e03c  mov     rcx, [rbx+5D0h]
0x18017e043  test    rcx, rcx
0x18017e046  jz      short loc_18017E04D
0x18017e048  call    sub_18017E1D0
0x18017e04d  mov     qword ptr [rbx+5D0h], 0
0x18017e058  mov     rcx, rdi; lpCriticalSection
0x18017e05b  call    cs:LeaveCriticalSection
0x18017e062  nop     dword ptr [rax+rax+00h]
0x18017e067  mov     rcx, [rbx+48h]
0x18017e06b  test    rcx, rcx
0x18017e06e  jz      short loc_18017E085
0x18017e070  mov     rax, [rcx]
0x18017e073  mov     rax, [rax+10h]
0x18017e077  call    cs:__guard_dispatch_icall_fptr
0x18017e07d  mov     qword ptr [rbx+48h], 0
0x18017e085  mov     rax, [rbx+0C90h]
0x18017e08c  test    rax, rax
0x18017e08f  jz      short loc_18017E0FB
0x18017e091  mov     rcx, [rax+11C8h]
0x18017e098  test    rcx, rcx
0x18017e09b  jz      short loc_18017E0A2
0x18017e09d  call    sub_1800DFDCC
0x18017e0a2  mov     rcx, [rbx+0C90h]
0x18017e0a9  call    sub_1800E3280
0x18017e0ae  mov     rcx, [rbx+0C90h]
0x18017e0b5  call    sub_1800EFCD0
0x18017e0ba  mov     rcx, [rbx+7F0h]
0x18017e0c1  test    rcx, rcx
0x18017e0c4  jz      short loc_18017E0DA
0x18017e0c6  add     rcx, 8
0x18017e0ca  call    sub_180199120
0x18017e0cf  mov     qword ptr [rbx+7F0h], 0
0x18017e0da  mov     rcx, [rbx+0C90h]
0x18017e0e1  test    rcx, rcx
0x18017e0e4  jz      short loc_18017E0F0
0x18017e0e6  mov     edx, 1
0x18017e0eb  call    sub_1800EF9D0
0x18017e0f0  mov     qword ptr [rbx+0C90h], 0
0x18017e0fb  mov     rcx, rdi; lpCriticalSection
0x18017e0fe  call    cs:__imp_DeleteCriticalSection
0x18017e105  nop     dword ptr [rax+rax+00h]
0x18017e10a  mov     rcx, [rbx+7F8h]; hObject
0x18017e111  call    cs:CloseHandle
0x18017e118  nop     dword ptr [rax+rax+00h]
0x18017e11d  mov     rcx, [rbx+800h]; hObject
0x18017e124  call    cs:CloseHandle
0x18017e12b  nop     dword ptr [rax+rax+00h]
0x18017e130  mov     rdx, [rbx+5F0h]
0x18017e137  test    rdx, rdx
0x18017e13a  jz      short loc_18017E155
0x18017e13c  mov     rcx, [rbx+5C8h]
0x18017e143  test    rcx, rcx
0x18017e146  jz      short loc_18017E155
0x18017e148  mov     rax, [rcx]
0x18017e14b  mov     rax, [rax+28h]
0x18017e14f  call    cs:__guard_dispatch_icall_fptr
0x18017e155  mov     rcx, [rbx+5C8h]
0x18017e15c  test    rcx, rcx
0x18017e15f  jz      short loc_18017E179
0x18017e161  mov     rax, [rcx]
0x18017e164  mov     rax, [rax+10h]
0x18017e168  call    cs:__guard_dispatch_icall_fptr
0x18017e16e  mov     qword ptr [rbx+5C8h], 0
0x18017e179  mov     edx, 1
0x18017e17e  mov     rcx, rbx
0x18017e181  call    sub_18017EEA0
0x18017e186  lock dec cs:dword_180245FC4
0x18017e18d  mov     rcx, rbx
0x18017e190  mov     rbx, [rsp+28h+arg_0]
0x18017e195  add     rsp, 20h
0x18017e199  pop     rdi
0x18017e19a  jmp     sub_1801838E8
```
