# WdipAddParameterToCollection

- ea: `0x18000934c`
- end: `0x1800094b6`
- name: `WdipAddParameterToCollection`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800094c0`

## callees

- `0x1800013a0`
- `0x180008ea0`
- `0x180009090`
- `0x18000934c`
- `0x18000a856`
- `0x180018b49`

## string_xrefs

- `0x180009460`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x18000949d`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`

## pseudocode

```c
__int64 __fastcall WdipAddParameterToCollection(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  int v5; // r8d
  __int64 v6; // rdi
  unsigned int v7; // edx
  size_t v8; // r14
  void *v9; // rax
  void *v10; // rsi
  unsigned __int64 v11; // rax
  unsigned int v12; // edx
  unsigned int v13; // eax
  int Args; // [rsp+20h] [rbp-38h]

  if ( !a1 )
  {
    v4 = -2147024809;
    Args = 87;
    v5 = 1230;
LABEL_18:
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (__int64)L"WdipAddParameterToCollection",
      v5,
      (const wchar_t *)L"Error = %d",
      Args);
    return v4;
  }
  if ( !a2 )
  {
    v4 = -2147024809;
    Args = 87;
    v5 = 1231;
    goto LABEL_18;
  }
  v6 = *(unsigned int *)(a1 + 4);
  if ( (int)v6 + 1 < (unsigned int)v6 )
    return (unsigned int)-2147024362;
  v7 = 8 * v6 + 8;
  if ( (_DWORD)v6 + 1 != v7 >> 3 )
    return (unsigned int)-2147024362;
  v8 = v7;
  v9 = (void *)WdipAlloc(v7);
  v10 = v9;
  if ( !v9 )
  {
    v4 = -2147024882;
    Args = 14;
    v5 = 1255;
    goto LABEL_18;
  }
  memset_0(v9, 0, v8);
  v11 = 8LL * *(unsigned int *)(a1 + 4);
  if ( v11 > 0xFFFFFFFF )
  {
    v5 = 1262;
    goto LABEL_17;
  }
  memcpy_0(v10, *(const void **)(a1 + 8), (unsigned int)v11);
  *((_QWORD *)v10 + v6) = a2;
  WdipFree(*(_QWORD *)(a1 + 8));
  *(_QWORD *)(a1 + 8) = v10;
  v12 = *(_DWORD *)a1 + *(_DWORD *)(a2 + 32);
  if ( v12 < *(_DWORD *)a1 )
  {
    *(_DWORD *)a1 = -1;
    v5 = 1276;
LABEL_17:
    Args = 534;
    v4 = -2147024362;
    goto LABEL_18;
  }
  v13 = *(_DWORD *)(a1 + 4);
  *(_DWORD *)a1 = v12;
  if ( v13 + 1 >= v13 )
  {
    *(_DWORD *)(a1 + 4) = v13 + 1;
    return 0;
  }
  *(_DWORD *)(a1 + 4) = -1;
  WdipTraceError(
    (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
    (__int64)L"WdipAddParameterToCollection",
    1279,
    (const wchar_t *)L"Error = %d",
    534);
  return (unsigned int)-2147024362;
}

```

## disassembly

```asm
0x18000934c  push    rbx
0x18000934e  push    rbp
0x18000934f  push    rsi
0x180009350  push    rdi
0x180009351  push    r14
0x180009353  sub     rsp, 30h
0x180009357  mov     rbp, rdx
0x18000935a  mov     rbx, rcx
0x18000935d  test    rcx, rcx
0x180009360  jnz     short loc_18000937A
0x180009362  mov     ebx, 80070057h
0x180009367  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x18000936f  mov     r8d, 4CEh
0x180009375  jmp     loc_18000948F
0x18000937a  test    rbp, rbp
0x18000937d  jnz     short loc_180009397
0x18000937f  mov     ebx, 80070057h
0x180009384  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x18000938c  mov     r8d, 4CFh
0x180009392  jmp     loc_18000948F
0x180009397  mov     edi, [rcx+4]
0x18000939a  lea     ecx, [rdi+1]
0x18000939d  cmp     ecx, edi
0x18000939f  jnb     short loc_1800093AB
0x1800093a1  mov     ebx, 80070216h
0x1800093a6  jmp     loc_1800094A9
0x1800093ab  lea     edx, ds:8[rdi*8]
0x1800093b2  mov     eax, edx
0x1800093b4  shr     eax, 3
0x1800093b7  cmp     ecx, eax
0x1800093b9  jnz     short loc_1800093A1
0x1800093bb  mov     ecx, edx
0x1800093bd  mov     r14d, edx
0x1800093c0  call    WdipAlloc
0x1800093c5  mov     rsi, rax
0x1800093c8  test    rax, rax
0x1800093cb  jnz     short loc_1800093E5
0x1800093cd  mov     ebx, 8007000Eh
0x1800093d2  mov     dword ptr [rsp+58h+Args], 0Eh
0x1800093da  mov     r8d, 4E7h
0x1800093e0  jmp     loc_18000948F
0x1800093e5  mov     r8, r14; Size
0x1800093e8  xor     edx, edx; Val
0x1800093ea  mov     rcx, rsi; void *
0x1800093ed  call    memset_0
0x1800093f2  mov     eax, [rbx+4]
0x1800093f5  mov     r14d, 0FFFFFFFFh
0x1800093fb  shl     rax, 3
0x1800093ff  cmp     rax, r14
0x180009402  ja      short loc_18000947C
0x180009404  mov     rdx, [rbx+8]; Src
0x180009408  mov     rcx, rsi; void *
0x18000940b  mov     r8d, eax; Size
0x18000940e  call    memcpy_0
0x180009413  mov     [rsi+rdi*8], rbp
0x180009417  mov     rcx, [rbx+8]
0x18000941b  call    WdipFree
0x180009420  mov     [rbx+8], rsi
0x180009424  mov     edx, [rbp+20h]
0x180009427  add     edx, [rbx]
0x180009429  cmp     edx, [rbx]
0x18000942b  jb      short loc_180009471
0x18000942d  mov     eax, [rbx+4]
0x180009430  mov     [rbx], edx
0x180009432  lea     ecx, [rax+1]
0x180009435  cmp     ecx, eax
0x180009437  jb      short loc_180009440
0x180009439  mov     [rbx+4], ecx
0x18000943c  xor     ebx, ebx
0x18000943e  jmp     short loc_1800094A9
0x180009440  lea     r9, aErrorD; "Error = %d"
0x180009447  mov     [rbx+4], r14d
0x18000944b  mov     r8d, 4FFh; int
0x180009451  mov     dword ptr [rsp+58h+Args], 216h; Args
0x180009459  lea     rdx, aWdipaddparamet; "WdipAddParameterToCollection"
0x180009460  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180009467  call    WdipTraceError
0x18000946c  jmp     loc_1800093A1
0x180009471  mov     [rbx], r14d
0x180009474  mov     r8d, 4FCh
0x18000947a  jmp     short loc_180009482
0x18000947c  mov     r8d, 4EEh; int
0x180009482  mov     dword ptr [rsp+58h+Args], 216h; Args
0x18000948a  mov     ebx, 80070216h
0x18000948f  lea     r9, aErrorD; "Error = %d"
0x180009496  lea     rdx, aWdipaddparamet; "WdipAddParameterToCollection"
0x18000949d  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800094a4  call    WdipTraceError
0x1800094a9  mov     eax, ebx
0x1800094ab  add     rsp, 30h
0x1800094af  pop     r14
0x1800094b1  pop     rdi
0x1800094b2  pop     rsi
0x1800094b3  pop     rbp
0x1800094b4  pop     rbx
0x1800094b5  retn
```
