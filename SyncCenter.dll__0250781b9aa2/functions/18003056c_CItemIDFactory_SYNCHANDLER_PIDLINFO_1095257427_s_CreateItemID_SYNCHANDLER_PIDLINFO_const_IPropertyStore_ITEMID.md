# CItemIDFactory<SYNCHANDLER_PIDLINFO,1095257427>::s_CreateItemID(SYNCHANDLER_PIDLINFO const *,IPropertyStore *,_ITEMID_CHILD * *,IMalloc *)

- ea: `0x18003056c`
- end: `0x18003062e`
- name: `?s_CreateItemID@?$CItemIDFactory@USYNCHANDLER_PIDLINFO@@$0EBEIENFD@@@SAJPEFBUSYNCHANDLER_PIDLINFO@@PEAUIPropertyStore@@PEAPEAU_ITEMID_CHILD@@PEAUIMalloc@@@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800304e4`

## callees

- `0x18003056c`
- `0x18005292a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003058d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003058d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030616`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030616`

## pseudocode

```c
__int64 __fastcall CItemIDFactory<SYNCHANDLER_PIDLINFO,1095257427>::s_CreateItemID(_OWORD *a1, __int64 a2, _QWORD *a3)
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
    *(_DWORD *)(v6 + 6) = 1095257427;
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
0x18003056c  mov     [rsp+arg_0], rbx
0x180030571  mov     [rsp+arg_8], rsi
0x180030576  push    rdi
0x180030577  sub     rsp, 20h
0x18003057b  mov     rdi, rcx
0x18003057e  mov     qword ptr [r8], 0
0x180030585  mov     ecx, 92h; cb
0x18003058a  mov     rsi, r8
0x18003058d  call    cs:__imp_CoTaskMemAlloc
0x180030593  mov     rbx, rax
0x180030596  test    rax, rax
0x180030599  jz      short loc_18003060F
0x18003059b  xor     edx, edx; Val
0x18003059d  mov     r8d, 92h; Size
0x1800305a3  mov     rcx, rax; void *
0x1800305a6  call    memset_0
0x1800305ab  mov     word ptr [rbx], 90h
0x1800305b0  mov     word ptr [rbx+4], 8Ah
0x1800305b6  mov     dword ptr [rbx+6], 41484D53h
0x1800305bd  mov     dword ptr [rbx+0Ah], 800000h
0x1800305c4  test    rdi, rdi
0x1800305c7  jz      short loc_180030608
0x1800305c9  movaps  xmm0, xmmword ptr [rdi]
0x1800305cc  movups  xmmword ptr [rbx+0Eh], xmm0
0x1800305d0  movaps  xmm1, xmmword ptr [rdi+10h]
0x1800305d4  movups  xmmword ptr [rbx+1Eh], xmm1
0x1800305d8  movaps  xmm0, xmmword ptr [rdi+20h]
0x1800305dc  movups  xmmword ptr [rbx+2Eh], xmm0
0x1800305e0  movaps  xmm1, xmmword ptr [rdi+30h]
0x1800305e4  movups  xmmword ptr [rbx+3Eh], xmm1
0x1800305e8  movaps  xmm0, xmmword ptr [rdi+40h]
0x1800305ec  movups  xmmword ptr [rbx+4Eh], xmm0
0x1800305f0  movaps  xmm1, xmmword ptr [rdi+50h]
0x1800305f4  movups  xmmword ptr [rbx+5Eh], xmm1
0x1800305f8  movaps  xmm0, xmmword ptr [rdi+60h]
0x1800305fc  movups  xmmword ptr [rbx+6Eh], xmm0
0x180030600  movaps  xmm1, xmmword ptr [rdi+70h]
0x180030604  movups  xmmword ptr [rbx+7Eh], xmm1
0x180030608  mov     [rsi], rbx
0x18003060b  xor     ebx, ebx
0x18003060d  jmp     short loc_180030614
0x18003060f  mov     ebx, 8007000Eh
0x180030614  xor     ecx, ecx; pv
0x180030616  call    cs:__imp_CoTaskMemFree
0x18003061c  mov     rsi, [rsp+28h+arg_8]
0x180030621  mov     eax, ebx
0x180030623  mov     rbx, [rsp+28h+arg_0]
0x180030628  add     rsp, 20h
0x18003062c  pop     rdi
0x18003062d  retn
```
