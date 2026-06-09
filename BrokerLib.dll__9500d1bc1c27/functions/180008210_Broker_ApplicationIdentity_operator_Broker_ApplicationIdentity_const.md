# Broker::ApplicationIdentity::operator<(Broker::ApplicationIdentity const &)

- ea: `0x180008210`
- end: `0x18000832e`
- name: `??MApplicationIdentity@Broker@@QEBA_NAEBU01@@Z`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006eb0`

## callees

- `0x180008210`
- `0x180014a40`
- `0x18001659e`
- `0x1800165da`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800082b2`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800082b2`

## pseudocode

```c
char __fastcall Broker::ApplicationIdentity::operator<(__int64 a1, __int64 a2)
{
  const void *v3; // rcx
  const void *v5; // rdx
  size_t v6; // r8
  size_t v7; // rax
  int v8; // eax
  int v9; // ebx
  const WCHAR *lpString2; // rax
  const WCHAR *v11; // r8
  int v12; // eax
  int v14; // eax
  _BYTE pExceptionObject[56]; // [rsp+50h] [rbp-38h] BYREF

  v3 = *(const void **)a1;
  v5 = *(const void **)a2;
  v6 = *(_QWORD *)(a1 + 8) - (_QWORD)v3;
  v7 = *(_QWORD *)(a2 + 8) - (_QWORD)v5;
  if ( v6 < v7 )
  {
    v9 = -1;
  }
  else if ( v6 > v7 )
  {
    v9 = 1;
  }
  else
  {
    v8 = memcmp_0(v3, v5, v6);
    if ( v8 < 0 )
      v9 = -1;
    else
      v9 = v8 > 0;
  }
  lpString2 = (const WCHAR *)(a2 + 24);
  if ( *(_QWORD *)(a2 + 48) > 7u )
    lpString2 = *(const WCHAR **)lpString2;
  v11 = (const WCHAR *)(a1 + 24);
  if ( *(_QWORD *)(a1 + 48) > 7u )
    v11 = *(const WCHAR **)v11;
  v12 = CompareStringEx(&LocaleName, 1u, v11, *(_DWORD *)(a1 + 40), lpString2, *(_DWORD *)(a2 + 40), 0, 0, 0);
  if ( v12 == 1 )
    return 1;
  v14 = v12 - 2;
  if ( v14 )
  {
    if ( v14 != 1 )
    {
      Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
      throw (Broker::Win32Error *)pExceptionObject;
    }
  }
  else if ( v9 == -1 )
  {
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180008210  mov     rax, rsp
0x180008213  push    rbx
0x180008214  sub     rsp, 80h
0x18000821b  mov     [rax+8], rbp
0x18000821f  xor     ebp, ebp
0x180008221  mov     [rax+10h], rsi
0x180008225  mov     rsi, rcx
0x180008228  mov     rcx, [rcx]; Buf1
0x18000822b  mov     [rax+18h], rdi
0x18000822f  mov     rdi, rdx
0x180008232  mov     rdx, [rdx]; Buf2
0x180008235  mov     r8, [rsi+8]
0x180008239  sub     r8, rcx; Size
0x18000823c  mov     rax, [rdi+8]
0x180008240  sub     rax, rdx
0x180008243  cmp     r8, rax
0x180008246  jb      loc_1800082DD
0x18000824c  ja      loc_1800082EE
0x180008252  call    memcmp_0
0x180008257  test    eax, eax
0x180008259  js      loc_1800082E4
0x18000825f  test    eax, eax
0x180008261  mov     ebx, ebp
0x180008263  setnle  bl
0x180008266  cmp     qword ptr [rdi+30h], 7
0x18000826b  lea     rax, [rdi+18h]
0x18000826f  mov     ecx, [rdi+28h]
0x180008272  mov     rdi, [rsp+88h+arg_10]
0x18000827a  jbe     short loc_18000827F
0x18000827c  mov     rax, [rax]
0x18000827f  cmp     qword ptr [rsi+30h], 7
0x180008284  lea     r8, [rsi+18h]; lpString1
0x180008288  ja      short loc_1800082D8
0x18000828a  mov     r9d, [rsi+28h]; cchCount1
0x18000828e  mov     edx, 1; dwCmpFlags
0x180008293  mov     [rsp+88h+lParam], rbp; lParam
0x180008298  mov     [rsp+88h+lpReserved], rbp; lpReserved
0x18000829d  mov     [rsp+88h+lpVersionInformation], rbp; lpVersionInformation
0x1800082a2  mov     [rsp+88h+cchCount2], ecx; cchCount2
0x1800082a6  lea     rcx, LocaleName; lpLocaleName
0x1800082ad  mov     [rsp+88h+lpString2], rax; lpString2
0x1800082b2  call    cs:__imp_CompareStringEx
0x1800082b8  mov     rsi, [rsp+88h+arg_8]
0x1800082c0  mov     rbp, [rsp+88h+arg_0]
0x1800082c8  cmp     eax, 1
0x1800082cb  jnz     short loc_180008308
0x1800082cd  mov     al, 1
0x1800082cf  add     rsp, 80h
0x1800082d6  pop     rbx
0x1800082d7  retn
0x1800082d8  mov     r8, [r8]
0x1800082db  jmp     short loc_18000828A
0x1800082dd  mov     ebx, 0FFFFFFFFh
0x1800082e2  jmp     short loc_180008266
0x1800082e4  mov     ebx, 0FFFFFFFFh
0x1800082e9  jmp     loc_180008266
0x1800082ee  mov     ebx, 1
0x1800082f3  jmp     loc_180008266
0x1800082f8  cmp     ebx, 0FFFFFFFFh
0x1800082fb  jz      short loc_1800082CD
0x1800082fd  xor     al, al
0x1800082ff  add     rsp, 80h
0x180008306  pop     rbx
0x180008307  retn
0x180008308  sub     eax, 2
0x18000830b  jz      short loc_1800082F8
0x18000830d  cmp     eax, 1
0x180008310  jz      short loc_1800082FD
0x180008312  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180008317  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18000831c  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180008323  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180008328  call    _CxxThrowException_0
```
