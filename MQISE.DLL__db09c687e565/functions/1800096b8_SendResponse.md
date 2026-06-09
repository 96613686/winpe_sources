# SendResponse

- ea: `0x1800096b8`
- end: `0x180009741`
- name: `SendResponse`
- size: `137`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800071c4`
- `0x18000faf6`
- `0x18000fe9e`
- `0x18000ff52`

## callees

- `0x180001c0c`
- `0x1800096b8`
- `0x180011010`

## import_xrefs

- `msvcrt!??0exception@@QEAA@XZ` at `0x180009729`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180009729`

## pseudocode

```c
__int64 __fastcall SendResponse(__int64 a1, __int64 a2, int a3)
{
  unsigned __int64 v3; // rax
  __int64 v5; // rcx
  __int64 (__fastcall *v6)(__int64, __int64, _QWORD *); // rax
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v9[2]; // [rsp+48h] [rbp-30h] BYREF
  int v10; // [rsp+58h] [rbp-20h]
  int v11; // [rsp+5Ch] [rbp-1Ch]
  int v12; // [rsp+60h] [rbp-18h]
  int v13; // [rsp+64h] [rbp-14h]

  v9[0] = a2;
  v13 = 0;
  v3 = -1;
  do
    ++v3;
  while ( *(_BYTE *)(a2 + v3) );
  if ( v3 > 0xFFFFFFFF )
  {
    exception::exception((exception *)pExceptionObject);
    throw (exception *)pExceptionObject;
  }
  v5 = *(_QWORD *)(a1 + 8);
  v10 = v3;
  v9[1] = "Content-Length: 0\r\n\r\n";
  v6 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(a1 + 184);
  v12 = a3;
  v11 = 21;
  return v6(v5, 1016, v9);
}

```

## disassembly

```asm
0x1800096b8  sub     rsp, 78h
0x1800096bc  xor     r9d, r9d
0x1800096bf  mov     [rsp+78h+var_30], rdx
0x1800096c4  mov     [rsp+78h+var_14], r9d
0x1800096c9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800096cd  mov     r10, rcx
0x1800096d0  inc     rax
0x1800096d3  cmp     [rdx+rax], r9b
0x1800096d7  jnz     short loc_1800096D0
0x1800096d9  mov     ecx, 0FFFFFFFFh
0x1800096de  cmp     rax, rcx
0x1800096e1  ja      short loc_180009724
0x1800096e3  mov     rcx, [r10+8]
0x1800096e7  mov     edx, 3F8h
0x1800096ec  mov     [rsp+78h+var_20], eax
0x1800096f0  lea     rax, aContentLength0; "Content-Length: 0\r\n\r\n"
0x1800096f7  mov     [rsp+78h+var_28], rax
0x1800096fc  mov     rax, [r10+0B8h]
0x180009703  mov     [rsp+78h+var_18], r8d
0x180009708  lea     r8, [rsp+78h+var_30]
0x18000970d  mov     [rsp+78h+var_1C], 15h
0x180009715  mov     [rsp+78h+var_58], r9
0x18000971a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000971f  add     rsp, 78h
0x180009723  retn
0x180009724  lea     rcx, [rsp+78h+pExceptionObject]
0x180009729  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x18000972f  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x180009736  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000973b  call    _CxxThrowException_0
```
