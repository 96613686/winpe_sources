# CreateNpSd(void)

- ea: `0x180008724`
- end: `0x180008886`
- name: `?CreateNpSd@@YAPEAXXZ`
- size: `354`
- prototype: `_OWORD *(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009128`

## callees

- `0x180008724`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000880b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000880b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000881c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000881c`

## pseudocode

```c
_OWORD *CreateNpSd(void)
{
  HANDLE ProcessHeap; // rax
  _OWORD *result; // rax
  __int128 v2; // [rsp+30h] [rbp-29h]
  __int128 v3; // [rsp+40h] [rbp-19h]
  __int128 v4; // [rsp+50h] [rbp-9h]
  __int128 v5; // [rsp+60h] [rbp+7h]
  __int128 v6; // [rsp+70h] [rbp+17h]
  __int128 v7; // [rsp+80h] [rbp+27h]
  __int128 v8; // [rsp+90h] [rbp+37h]

  *(_QWORD *)&v2 = 0x70000200000014LL;
  *((_QWORD *)&v2 + 1) = 0x28000000000004LL;
  *(_QWORD *)&v3 = 0x60110000000LL;
  *((_QWORD *)&v3 + 1) = 0x5005000000LL;
  *(_QWORD *)&v4 = 0x360113461F12C0C6LL;
  *((_QWORD *)&v4 + 1) = 0x5AE7EA38E65ACE03LL;
  *(_QWORD *)&v5 = 0x140000CDB58062LL;
  *((_QWORD *)&v5 + 1) = 0x1010012019BLL;
  *(_QWORD *)&v6 = 0x1000000;
  *((_QWORD *)&v6 + 1) = 0x12019B00140000LL;
  *(_QWORD *)&v7 = 0x500000000000101LL;
  *((_QWORD *)&v7 + 1) = 0x18000000000007LL;
  *(_QWORD *)&v8 = 0x2010012019BLL;
  *((_QWORD *)&v8 + 1) = 0x20F000000LL;
  ProcessHeap = GetProcessHeap();
  result = HeapAlloc(ProcessHeap, 0, 0x84u);
  if ( result )
  {
    *result = 0x80040001;
    result[1] = v2;
    result[2] = v3;
    result[3] = v4;
    result[4] = v5;
    result[5] = v6;
    result[6] = v7;
    result[7] = v8;
    *((_DWORD *)result + 32) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x180008724  mov     [rsp-8+arg_0], rbx
0x180008729  push    rbp
0x18000872a  lea     rbp, [rsp-57h]
0x18000872f  sub     rsp, 0B0h
0x180008736  xor     ebx, ebx
0x180008738  mov     dword ptr [rbp+57h+var_90], 80040001h
0x18000873f  mov     qword ptr [rbp+57h+var_90+4], rbx
0x180008743  mov     dword ptr [rbp+57h+var_90+0Ch], ebx
0x180008746  mov     dword ptr [rbp+57h+var_80], 14h
0x18000874d  mov     dword ptr [rbp+57h+var_80+4], 700002h
0x180008754  mov     dword ptr [rbp+57h+var_80+8], 4
0x18000875b  mov     dword ptr [rbp+57h+var_80+0Ch], 280000h
0x180008762  mov     dword ptr [rbp+57h+var_70], 10000000h
0x180008769  mov     dword ptr [rbp+57h+var_70+4], 601h
0x180008770  mov     dword ptr [rbp+57h+var_70+8], 5000000h
0x180008777  mov     dword ptr [rbp+57h+var_70+0Ch], 50h ; 'P'
0x18000877e  mov     dword ptr [rbp+57h+var_60], 1F12C0C6h
0x180008785  mov     dword ptr [rbp+57h+var_60+4], 36011346h
0x18000878c  mov     dword ptr [rbp+57h+var_60+8], 0E65ACE03h
0x180008793  mov     dword ptr [rbp+57h+var_60+0Ch], 5AE7EA38h
0x18000879a  mov     dword ptr [rbp+57h+var_50], 0CDB58062h
0x1800087a1  mov     dword ptr [rbp+57h+var_50+4], 140000h
0x1800087a8  mov     dword ptr [rbp+57h+var_50+8], 12019Bh
0x1800087af  mov     dword ptr [rbp+57h+var_50+0Ch], 101h
0x1800087b6  mov     qword ptr [rbp+57h+var_40], 1000000h
0x1800087be  mov     dword ptr [rbp+57h+var_40+8], 140000h
0x1800087c5  mov     dword ptr [rbp+57h+var_40+0Ch], 12019Bh
0x1800087cc  mov     dword ptr [rbp+57h+var_30], 101h
0x1800087d3  mov     dword ptr [rbp+57h+var_30+4], 5000000h
0x1800087da  mov     dword ptr [rbp+57h+var_30+8], 7
0x1800087e1  mov     dword ptr [rbp+57h+var_30+0Ch], 180000h
0x1800087e8  mov     dword ptr [rbp+57h+var_20], 12019Bh
0x1800087ef  mov     dword ptr [rbp+57h+var_20+4], 201h
0x1800087f6  mov     dword ptr [rbp+57h+var_20+8], 0F000000h
0x1800087fd  mov     dword ptr [rbp+57h+var_20+0Ch], 2
0x180008804  mov     [rbp+57h+var_10], 1
0x18000880b  call    cs:__imp_GetProcessHeap
0x180008811  xor     edx, edx; dwFlags
0x180008813  mov     r8d, 84h; dwBytes
0x180008819  mov     rcx, rax; hHeap
0x18000881c  call    cs:__imp_HeapAlloc
0x180008822  mov     rcx, rax
0x180008825  test    rax, rax
0x180008828  jz      short loc_180008872
0x18000882a  movaps  xmm0, [rbp+57h+var_90]
0x18000882e  movaps  xmm1, [rbp+57h+var_80]
0x180008832  movups  xmmword ptr [rax], xmm0
0x180008835  movaps  xmm0, [rbp+57h+var_70]
0x180008839  movups  xmmword ptr [rax+10h], xmm1
0x18000883d  movaps  xmm1, [rbp+57h+var_60]
0x180008841  movups  xmmword ptr [rax+20h], xmm0
0x180008845  movaps  xmm0, [rbp+57h+var_50]
0x180008849  movups  xmmword ptr [rax+30h], xmm1
0x18000884d  movaps  xmm1, [rbp+57h+var_40]
0x180008851  movups  xmmword ptr [rax+40h], xmm0
0x180008855  movaps  xmm0, [rbp+57h+var_30]
0x180008859  movups  xmmword ptr [rax+50h], xmm1
0x18000885d  movaps  xmm1, [rbp+57h+var_20]
0x180008861  movups  xmmword ptr [rax+60h], xmm0
0x180008865  movups  xmmword ptr [rax+70h], xmm1
0x180008869  mov     eax, [rbp+57h+var_10]
0x18000886c  mov     [rcx+80h], eax
0x180008872  mov     rbx, [rsp+0B0h+arg_0]
0x18000887a  mov     rax, rcx
0x18000887d  add     rsp, 0B0h
0x180008884  pop     rbp
0x180008885  retn
```
