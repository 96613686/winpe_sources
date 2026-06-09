# SetConstraint(HRECOCONTEXT__ *,ulong,ushort const *)

- ea: `0x180043c14`
- end: `0x180043d47`
- name: `?SetConstraint@@YAJPEAUHRECOCONTEXT__@@KPEBG@Z`
- size: `307`
- prototype: `int(HRECOCONTEXT, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180043be0`
- `0x1800a4810`

## callees

- `0x180043c14`
- `0x180044ac6`
- `0x180083dc0`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043cb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043cdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043cb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043cdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043cf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043d26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043d2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043cf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043d26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043d2f`

## pseudocode

```c
__int64 __fastcall SetConstraint(__int64 *a1, unsigned int a2, const unsigned __int16 *a3)
{
  __int64 v3; // rbx
  __int64 v7; // rcx
  unsigned int (__fastcall *v8)(__int64, _QWORD); // rax
  int v9; // ebx
  _QWORD *v10; // rax
  _QWORD *v11; // rdi
  SIZE_T v12; // rbx
  void *v13; // rax
  void *v14; // rcx

  v3 = a2;
  if ( a2 > 0x7FFFFFFF )
    return 2147549183LL;
  if ( a1 )
  {
    v7 = *a1;
    if ( v7 )
    {
      if ( (a3 || !a2) && a2 < 0x3FFFFFFF && (!(2 * a2) || a3) && (!a3 || a2) )
      {
        v8 = *(unsigned int (__fastcall **)(__int64, _QWORD))(v7 + 152);
        if ( !v8 )
          return 2147500033LL;
        if ( !a1[2] )
          return v8(a1[1], a2);
        v10 = CoTaskMemAlloc(0x10u);
        v11 = v10;
        if ( !v10 )
          return 2147942414LL;
        *(_DWORD *)v10 = v3;
        v10[1] = 0;
        if ( (_DWORD)v3 )
        {
          v12 = 2 * v3;
          v13 = CoTaskMemAlloc(v12);
          v11[1] = v13;
          if ( !v13 )
          {
            CoTaskMemFree(v11);
            return 2147942414LL;
          }
          memcpy_0(v13, a3, v12);
        }
        v9 = AddToQueue(a1, 22, v11);
        if ( v9 < 0 )
        {
          v14 = (void *)v11[1];
          if ( v14 )
            CoTaskMemFree(v14);
          CoTaskMemFree(v11);
        }
        return (unsigned int)v9;
      }
    }
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180043c14  push    rbx
0x180043c16  push    rbp
0x180043c17  push    rsi
0x180043c18  push    rdi
0x180043c19  sub     rsp, 28h
0x180043c1d  mov     ebx, edx
0x180043c1f  mov     rbp, r8
0x180043c22  mov     rsi, rcx
0x180043c25  cmp     edx, 7FFFFFFFh
0x180043c2b  jbe     short loc_180043C37
0x180043c2d  mov     eax, 8000FFFFh
0x180043c32  jmp     loc_180043D3E
0x180043c37  test    rsi, rsi
0x180043c3a  jz      loc_180043D39
0x180043c40  mov     rcx, [rcx]
0x180043c43  test    rcx, rcx
0x180043c46  jz      loc_180043D39
0x180043c4c  test    rbp, rbp
0x180043c4f  jnz     short loc_180043C59
0x180043c51  test    edx, edx
0x180043c53  jnz     loc_180043D39
0x180043c59  cmp     ebx, 3FFFFFFFh
0x180043c5f  jnb     loc_180043D39
0x180043c65  lea     eax, [rbx+rbx]
0x180043c68  test    eax, eax
0x180043c6a  jz      short loc_180043C75
0x180043c6c  test    rbp, rbp
0x180043c6f  jz      loc_180043D39
0x180043c75  test    rbp, rbp
0x180043c78  jz      short loc_180043C82
0x180043c7a  test    edx, edx
0x180043c7c  jz      loc_180043D39
0x180043c82  mov     rax, [rcx+98h]
0x180043c89  test    rax, rax
0x180043c8c  jnz     short loc_180043C98
0x180043c8e  mov     eax, 80004001h
0x180043c93  jmp     loc_180043D3E
0x180043c98  cmp     qword ptr [rsi+10h], 0
0x180043c9d  jnz     short loc_180043CB1
0x180043c9f  mov     rcx, [rsi+8]
0x180043ca3  mov     edx, ebx
0x180043ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043caa  mov     ebx, eax
0x180043cac  jmp     loc_180043D35
0x180043cb1  mov     ecx, 10h; cb
0x180043cb6  call    cs:__imp_CoTaskMemAlloc
0x180043cbc  mov     rdi, rax
0x180043cbf  test    rax, rax
0x180043cc2  jnz     short loc_180043CCB
0x180043cc4  mov     eax, 8007000Eh
0x180043cc9  jmp     short loc_180043D3E
0x180043ccb  mov     [rax], ebx
0x180043ccd  mov     qword ptr [rax+8], 0
0x180043cd5  test    ebx, ebx
0x180043cd7  jz      short loc_180043D07
0x180043cd9  add     rbx, rbx
0x180043cdc  mov     rcx, rbx; cb
0x180043cdf  call    cs:__imp_CoTaskMemAlloc
0x180043ce5  mov     [rdi+8], rax
0x180043ce9  test    rax, rax
0x180043cec  jnz     short loc_180043CF9
0x180043cee  mov     rcx, rdi; pv
0x180043cf1  call    cs:__imp_CoTaskMemFree
0x180043cf7  jmp     short loc_180043CC4
0x180043cf9  mov     r8, rbx; Size
0x180043cfc  mov     rdx, rbp; Src
0x180043cff  mov     rcx, rax; void *
0x180043d02  call    memcpy_0
0x180043d07  mov     r8, rdi
0x180043d0a  mov     edx, 16h
0x180043d0f  mov     rcx, rsi
0x180043d12  call    ?AddToQueue@@YAJPEAUtagWispContext@@W4OpType@@PEAX@Z; AddToQueue(tagWispContext *,OpType,void *)
0x180043d17  mov     ebx, eax
0x180043d19  test    eax, eax
0x180043d1b  jns     short loc_180043D35
0x180043d1d  mov     rcx, [rdi+8]; pv
0x180043d21  test    rcx, rcx
0x180043d24  jz      short loc_180043D2C
0x180043d26  call    cs:__imp_CoTaskMemFree
0x180043d2c  mov     rcx, rdi; pv
0x180043d2f  call    cs:__imp_CoTaskMemFree
0x180043d35  mov     eax, ebx
0x180043d37  jmp     short loc_180043D3E
0x180043d39  mov     eax, 80004003h
0x180043d3e  add     rsp, 28h
0x180043d42  pop     rdi
0x180043d43  pop     rsi
0x180043d44  pop     rbp
0x180043d45  pop     rbx
0x180043d46  retn
```
