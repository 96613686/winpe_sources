# CItemIDFactory<SYNCITEM_PIDLINFO,1229475155>::s_CreateItemID(SYNCITEM_PIDLINFO const *,IPropertyStore *,_ITEMID_CHILD * *,IMalloc *)

- ea: `0x180045f50`
- end: `0x180046012`
- name: `?s_CreateItemID@?$CItemIDFactory@USYNCITEM_PIDLINFO@@$0EJEIENFD@@@SAJPEFBUSYNCITEM_PIDLINFO@@PEAUIPropertyStore@@PEAPEAU_ITEMID_CHILD@@PEAUIMalloc@@@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180045ec8`

## callees

- `0x180045f50`
- `0x18005292a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045f71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045f71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045ffa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045ffa`

## pseudocode

```c
__int64 __fastcall CItemIDFactory<SYNCITEM_PIDLINFO,1229475155>::s_CreateItemID(_OWORD *a1, __int64 a2, _QWORD *a3)
{
  char *v5; // rax
  char *v6; // rbx
  unsigned int v7; // ebx

  *a3 = 0;
  v5 = (char *)CoTaskMemAlloc(0x92u);
  v6 = v5;
  if ( v5 )
  {
    memset_0(v5, 0, 0x92u);
    *(_WORD *)v6 = 144;
    *((_WORD *)v6 + 2) = 138;
    *(_DWORD *)(v6 + 6) = 1229475155;
    *(_DWORD *)(v6 + 10) = 0x800000;
    if ( a1 )
    {
      *(_OWORD *)(v6 + 14) = *a1;
      *(_OWORD *)(v6 + 30) = a1[1];
      *(_OWORD *)(v6 + 46) = a1[2];
      *(_OWORD *)(v6 + 62) = a1[3];
      *(_OWORD *)(v6 + 78) = a1[4];
      *(_OWORD *)(v6 + 94) = a1[5];
      *(_OWORD *)(v6 + 110) = a1[6];
      *(_OWORD *)(v6 + 126) = a1[7];
    }
    *a3 = v6;
    v7 = 0;
  }
  else
  {
    v7 = -2147024882;
  }
  CoTaskMemFree(0);
  return v7;
}

```

## disassembly

```asm
0x180045f50  mov     [rsp+arg_0], rbx
0x180045f55  mov     [rsp+arg_8], rsi
0x180045f5a  push    rdi
0x180045f5b  sub     rsp, 20h
0x180045f5f  mov     rdi, rcx
0x180045f62  mov     qword ptr [r8], 0
0x180045f69  mov     ecx, 92h; cb
0x180045f6e  mov     rsi, r8
0x180045f71  call    cs:__imp_CoTaskMemAlloc
0x180045f77  mov     rbx, rax
0x180045f7a  test    rax, rax
0x180045f7d  jz      short loc_180045FF3
0x180045f7f  xor     edx, edx; Val
0x180045f81  mov     r8d, 92h; Size
0x180045f87  mov     rcx, rax; void *
0x180045f8a  call    memset_0
0x180045f8f  mov     word ptr [rbx], 90h
0x180045f94  mov     word ptr [rbx+4], 8Ah
0x180045f9a  mov     dword ptr [rbx+6], 49484D53h
0x180045fa1  mov     dword ptr [rbx+0Ah], 800000h
0x180045fa8  test    rdi, rdi
0x180045fab  jz      short loc_180045FEC
0x180045fad  movaps  xmm0, xmmword ptr [rdi]
0x180045fb0  movups  xmmword ptr [rbx+0Eh], xmm0
0x180045fb4  movaps  xmm1, xmmword ptr [rdi+10h]
0x180045fb8  movups  xmmword ptr [rbx+1Eh], xmm1
0x180045fbc  movaps  xmm0, xmmword ptr [rdi+20h]
0x180045fc0  movups  xmmword ptr [rbx+2Eh], xmm0
0x180045fc4  movaps  xmm1, xmmword ptr [rdi+30h]
0x180045fc8  movups  xmmword ptr [rbx+3Eh], xmm1
0x180045fcc  movaps  xmm0, xmmword ptr [rdi+40h]
0x180045fd0  movups  xmmword ptr [rbx+4Eh], xmm0
0x180045fd4  movaps  xmm1, xmmword ptr [rdi+50h]
0x180045fd8  movups  xmmword ptr [rbx+5Eh], xmm1
0x180045fdc  movaps  xmm0, xmmword ptr [rdi+60h]
0x180045fe0  movups  xmmword ptr [rbx+6Eh], xmm0
0x180045fe4  movaps  xmm1, xmmword ptr [rdi+70h]
0x180045fe8  movups  xmmword ptr [rbx+7Eh], xmm1
0x180045fec  mov     [rsi], rbx
0x180045fef  xor     ebx, ebx
0x180045ff1  jmp     short loc_180045FF8
0x180045ff3  mov     ebx, 8007000Eh
0x180045ff8  xor     ecx, ecx; pv
0x180045ffa  call    cs:__imp_CoTaskMemFree
0x180046000  mov     rsi, [rsp+28h+arg_8]
0x180046005  mov     eax, ebx
0x180046007  mov     rbx, [rsp+28h+arg_0]
0x18004600c  add     rsp, 20h
0x180046010  pop     rdi
0x180046011  retn
```
