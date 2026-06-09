# WwanProfileCopyProfile

- ea: `0x18000db40`
- end: `0x18000dd68`
- name: `WwanProfileCopyProfile`
- size: `552`
- prototype: `DWORD __fastcall(void *, const void **Src)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180001694`
- `0x18000da50`
- `0x18000db40`
- `0x1800134f8`
- `0x180013700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbbd`

## pseudocode

```c
DWORD __fastcall WwanProfileCopyProfile(void *a1, const void **Src)
{
  _DWORD *v4; // rax
  size_t v5; // rsi
  void *v6; // rax
  unsigned int v8; // eax
  void *v9; // rax
  void *v10; // rcx
  int *v11; // rax
  int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // esi
  void *v15; // rax
  _DWORD *v16; // rsi
  __int64 v17; // r14
  __int64 v18; // r12
  _DWORD *v19; // rax
  unsigned int v20; // eax
  unsigned int v21; // r15d
  void *v22; // rax
  int *v23; // rax
  int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // r15d
  void *v27; // rax

  WwanProfileCleanup((__int64)a1);
  memcpy_0(a1, Src, 0x18B0u);
  *((_DWORD *)a1 + 1112) = 0;
  *((_QWORD *)a1 + 557) = 0;
  *((_QWORD *)a1 + 559) = 0;
  *((_QWORD *)a1 + 789) = 0;
  v4 = Src[559];
  if ( v4 )
  {
    v5 = (unsigned int)(56 * *v4 + 4);
    v6 = WwanMemAlloc(v5);
    *((_QWORD *)a1 + 559) = v6;
    if ( !v6 )
      return GetLastError();
    memcpy_0(v6, Src[559], v5);
  }
  v8 = *((_DWORD *)Src + 1112);
  if ( v8 )
  {
    v9 = WwanMemAlloc(v8);
    *((_QWORD *)a1 + 557) = v9;
    if ( !v9 )
    {
      v10 = (void *)*((_QWORD *)a1 + 559);
      if ( v10 )
      {
        operator delete(v10);
        *((_QWORD *)a1 + 559) = 0;
      }
      return GetLastError();
    }
    memcpy_0(v9, Src[557], *((unsigned int *)Src + 1112));
    *((_DWORD *)a1 + 1112) = *((_DWORD *)Src + 1112);
  }
  v11 = (int *)Src[789];
  if ( !v11 )
    return 0;
  v12 = *v11;
  if ( !v12 )
    return 0;
  v13 = 40 * v12 + 8;
  if ( v13 >= 8 )
  {
    v14 = v13;
    v15 = WwanMemAlloc(v13);
    *((_QWORD *)a1 + 789) = v15;
    if ( !v15 )
      return GetLastError();
    memcpy_0(v15, Src[789], v14);
    v16 = Src[789];
    if ( *v16 )
    {
      v17 = 0;
      do
      {
        v18 = *((_QWORD *)a1 + 789);
        v19 = *(_DWORD **)&v16[10 * v17 + 10];
        if ( v19 && *v19 )
        {
          v20 = 202 * *v19 + 4;
          if ( v20 < 4 )
            return 13;
          v21 = v20;
          v22 = WwanMemAlloc(v20);
          *(_QWORD *)(v18 + 40 * v17 + 40) = v22;
          if ( !v22 )
            return GetLastError();
          memcpy_0(v22, *(const void **)&v16[10 * v17 + 10], v21);
        }
        v23 = *(int **)&v16[10 * v17 + 8];
        if ( v23 )
        {
          v24 = *v23;
          if ( v24 )
          {
            v25 = 20 * v24 + 4;
            if ( v25 < 4 )
              return 13;
            v26 = v25;
            v27 = WwanMemAlloc(v25);
            *(_QWORD *)(v18 + 40 * v17 + 32) = v27;
            if ( !v27 )
              return GetLastError();
            memcpy_0(v27, *(const void **)&v16[10 * v17 + 8], v26);
          }
        }
        v16 = Src[789];
        v17 = (unsigned int)(v17 + 1);
      }
      while ( (unsigned int)v17 < *v16 );
    }
    return 0;
  }
  return 13;
}

```

## disassembly

```asm
0x18000db40  push    rbx
0x18000db42  push    rbp
0x18000db43  push    rsi
0x18000db44  push    rdi
0x18000db45  push    r12
0x18000db47  push    r14
0x18000db49  push    r15
0x18000db4b  sub     rsp, 20h
0x18000db4f  mov     rbx, rdx
0x18000db52  mov     rdi, rcx
0x18000db55  call    WwanProfileCleanup
0x18000db5a  mov     r8d, 18B0h; Size
0x18000db60  mov     rdx, rbx; Src
0x18000db63  mov     rcx, rdi; void *
0x18000db66  call    memcpy_0
0x18000db6b  mov     dword ptr [rdi+1160h], 0
0x18000db75  mov     qword ptr [rdi+1168h], 0
0x18000db80  mov     qword ptr [rdi+1178h], 0
0x18000db8b  mov     qword ptr [rdi+18A8h], 0
0x18000db96  mov     rax, [rbx+1178h]
0x18000db9d  test    rax, rax
0x18000dba0  jz      short loc_18000DBDA
0x18000dba2  imul    eax, [rax], 38h ; '8'
0x18000dba5  add     eax, 4
0x18000dba8  mov     ecx, eax; Size
0x18000dbaa  mov     esi, eax
0x18000dbac  call    WwanMemAlloc
0x18000dbb1  mov     [rdi+1178h], rax
0x18000dbb8  test    rax, rax
0x18000dbbb  jnz     short loc_18000DBC8
0x18000dbbd  call    cs:__imp_GetLastError
0x18000dbc3  jmp     loc_18000DD52
0x18000dbc8  mov     rdx, [rbx+1178h]; Src
0x18000dbcf  mov     r8, rsi; Size
0x18000dbd2  mov     rcx, rax; void *
0x18000dbd5  call    memcpy_0
0x18000dbda  mov     eax, [rbx+1160h]
0x18000dbe0  test    eax, eax
0x18000dbe2  jz      short loc_18000DC37
0x18000dbe4  mov     ecx, eax; Size
0x18000dbe6  call    WwanMemAlloc
0x18000dbeb  mov     [rdi+1168h], rax
0x18000dbf2  test    rax, rax
0x18000dbf5  jnz     short loc_18000DC15
0x18000dbf7  mov     rcx, [rdi+1178h]; Block
0x18000dbfe  test    rcx, rcx
0x18000dc01  jz      short loc_18000DBBD
0x18000dc03  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dc08  mov     qword ptr [rdi+1178h], 0
0x18000dc13  jmp     short loc_18000DBBD
0x18000dc15  mov     r8d, [rbx+1160h]; Size
0x18000dc1c  mov     rcx, rax; void *
0x18000dc1f  mov     rdx, [rbx+1168h]; Src
0x18000dc26  call    memcpy_0
0x18000dc2b  mov     eax, [rbx+1160h]
0x18000dc31  mov     [rdi+1160h], eax
0x18000dc37  mov     rax, [rbx+18A8h]
0x18000dc3e  test    rax, rax
0x18000dc41  jz      loc_18000DD50
0x18000dc47  mov     eax, [rax]
0x18000dc49  test    eax, eax
0x18000dc4b  jz      loc_18000DD50
0x18000dc51  lea     eax, [rax+rax*4]
0x18000dc54  lea     eax, ds:8[rax*8]
0x18000dc5b  cmp     eax, 8
0x18000dc5e  jb      loc_18000DD61
0x18000dc64  mov     ecx, eax; Size
0x18000dc66  mov     esi, eax
0x18000dc68  call    WwanMemAlloc
0x18000dc6d  mov     [rdi+18A8h], rax
0x18000dc74  test    rax, rax
0x18000dc77  jz      loc_18000DBBD
0x18000dc7d  mov     rdx, [rbx+18A8h]; Src
0x18000dc84  mov     r8d, esi; Size
0x18000dc87  mov     rcx, rax; void *
0x18000dc8a  call    memcpy_0
0x18000dc8f  mov     rsi, [rbx+18A8h]
0x18000dc96  cmp     dword ptr [rsi], 0
0x18000dc99  jbe     loc_18000DD50
0x18000dc9f  xor     r14d, r14d
0x18000dca2  mov     r12, [rdi+18A8h]
0x18000dca9  lea     rbp, [r14+r14*4]
0x18000dcad  mov     rax, [rsi+rbp*8+28h]
0x18000dcb2  test    rax, rax
0x18000dcb5  jz      short loc_18000DCF6
0x18000dcb7  cmp     dword ptr [rax], 0
0x18000dcba  jz      short loc_18000DCF6
0x18000dcbc  imul    eax, [rax], 0CAh
0x18000dcc2  add     eax, 4
0x18000dcc5  cmp     eax, 4
0x18000dcc8  jb      loc_18000DD61
0x18000dcce  mov     ecx, eax; Size
0x18000dcd0  mov     r15d, eax
0x18000dcd3  call    WwanMemAlloc
0x18000dcd8  mov     [r12+rbp*8+28h], rax
0x18000dcdd  test    rax, rax
0x18000dce0  jz      loc_18000DBBD
0x18000dce6  mov     rdx, [rsi+rbp*8+28h]; Src
0x18000dceb  mov     r8d, r15d; Size
0x18000dcee  mov     rcx, rax; void *
0x18000dcf1  call    memcpy_0
0x18000dcf6  mov     rax, [rsi+rbp*8+20h]
0x18000dcfb  test    rax, rax
0x18000dcfe  jz      short loc_18000DD3D
0x18000dd00  mov     eax, [rax]
0x18000dd02  test    eax, eax
0x18000dd04  jz      short loc_18000DD3D
0x18000dd06  lea     eax, [rax+rax*4]
0x18000dd09  lea     eax, ds:4[rax*4]
0x18000dd10  cmp     eax, 4
0x18000dd13  jb      short loc_18000DD61
0x18000dd15  mov     ecx, eax; Size
0x18000dd17  mov     r15d, eax
0x18000dd1a  call    WwanMemAlloc
0x18000dd1f  mov     [r12+rbp*8+20h], rax
0x18000dd24  test    rax, rax
0x18000dd27  jz      loc_18000DBBD
0x18000dd2d  mov     rdx, [rsi+rbp*8+20h]; Src
0x18000dd32  mov     r8d, r15d; Size
0x18000dd35  mov     rcx, rax; void *
0x18000dd38  call    memcpy_0
0x18000dd3d  mov     rsi, [rbx+18A8h]
0x18000dd44  inc     r14d
0x18000dd47  cmp     r14d, [rsi]
0x18000dd4a  jb      loc_18000DCA2
0x18000dd50  xor     eax, eax
0x18000dd52  add     rsp, 20h
0x18000dd56  pop     r15
0x18000dd58  pop     r14
0x18000dd5a  pop     r12
0x18000dd5c  pop     rdi
0x18000dd5d  pop     rsi
0x18000dd5e  pop     rbp
0x18000dd5f  pop     rbx
0x18000dd60  retn
0x18000dd61  mov     eax, 0Dh
0x18000dd66  jmp     short loc_18000DD52
```
