# CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::SetValue(ulong,IASFReadWriteTracker *)

- ea: `0x180009854`
- end: `0x18000994d`
- name: `?SetValue@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@QEAAJKPEAUIASFReadWriteTracker@@@Z`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007b70`
- `0x1800095e8`

## callees

- `0x1800015d0`
- `0x180009854`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::SetValue(
        _DWORD *a1,
        unsigned int a2,
        __int64 (__fastcall **a3)(_QWORD, _QWORD *))
{
  __int64 result; // rax
  _DWORD *v6; // rsi
  _DWORD *i; // rbx
  unsigned int v8; // eax
  __int64 (__fastcall **v9)(_DWORD *, _DWORD **); // rax
  _QWORD *v10; // rax
  __int64 v11; // rdi
  _DWORD *v12; // [rsp+20h] [rbp-28h] BYREF

  if ( !a1 )
    return 2147500035LL;
  v6 = 0;
  for ( i = a1; i; i = (_DWORD *)*((_QWORD *)i + 24) )
  {
    v8 = i[2];
    if ( a2 < v8 )
      break;
    if ( a2 < v8 + 20 )
      goto LABEL_12;
    v6 = i;
  }
  v9 = *(__int64 (__fastcall ***)(_DWORD *, _DWORD **))a1;
  v12 = 0;
  result = (*v9)(a1, &v12);
  if ( (int)result < 0 )
    return result;
  v12[2] = 20 * (a2 / 0x14);
  v10 = v12;
  if ( v6 )
    *((_QWORD *)v6 + 24) = v12;
  v10[24] = i;
  i = v12;
LABEL_12:
  v11 = a2 - i[2];
  if ( ((unsigned int)v11 & 0xFFFFFFF8) >= 0x18 )
    return 2147549183LL;
  *((_BYTE *)i + ((unsigned __int64)(unsigned int)v11 >> 3) + 24) |= CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::s_bSingleBitMasks[v11 & 7];
  if ( (unsigned int)v11 >= 0x14 )
    return 2147549183LL;
  *(_QWORD *)&i[2 * v11 + 8] = a3;
  return 0;
}

```

## disassembly

```asm
0x180009854  mov     [rsp+arg_10], rbx
0x180009859  push    rbp
0x18000985a  push    rsi
0x18000985b  push    rdi
0x18000985c  sub     rsp, 30h
0x180009860  mov     rax, cs:__security_cookie
0x180009867  xor     rax, rsp
0x18000986a  mov     [rsp+48h+var_20], rax
0x18000986f  mov     rbp, r8
0x180009872  mov     edi, edx
0x180009874  test    rcx, rcx
0x180009877  jnz     short loc_180009883
0x180009879  mov     eax, 80004003h
0x18000987e  jmp     loc_180009933
0x180009883  xor     esi, esi
0x180009885  mov     rbx, rcx
0x180009888  test    rbx, rbx
0x18000988b  jz      short loc_1800098A7
0x18000988d  mov     eax, [rbx+8]
0x180009890  cmp     edi, eax
0x180009892  jb      short loc_1800098A7
0x180009894  add     eax, 14h
0x180009897  cmp     edi, eax
0x180009899  jb      short loc_1800098F9
0x18000989b  mov     rsi, rbx
0x18000989e  mov     rbx, [rbx+0C0h]
0x1800098a5  jmp     short loc_180009888
0x1800098a7  mov     rax, [rcx]
0x1800098aa  lea     rdx, [rsp+48h+var_28]
0x1800098af  mov     [rsp+48h+var_28], 0
0x1800098b8  mov     rax, [rax]
0x1800098bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098c0  test    eax, eax
0x1800098c2  js      short loc_180009933
0x1800098c4  mov     eax, 0CCCCCCCDh
0x1800098c9  mul     edi
0x1800098cb  mov     rax, [rsp+48h+var_28]
0x1800098d0  shr     edx, 4
0x1800098d3  lea     ecx, [rdx+rdx*4]
0x1800098d6  shl     ecx, 2
0x1800098d9  mov     [rax+8], ecx
0x1800098dc  mov     rax, [rsp+48h+var_28]
0x1800098e1  test    rsi, rsi
0x1800098e4  jz      short loc_1800098ED
0x1800098e6  mov     [rsi+0C0h], rax
0x1800098ed  mov     [rax+0C0h], rbx
0x1800098f4  mov     rbx, [rsp+48h+var_28]
0x1800098f9  sub     edi, [rbx+8]
0x1800098fc  mov     eax, edi
0x1800098fe  and     eax, 0FFFFFFF8h
0x180009901  cmp     eax, 18h
0x180009904  jnb     short loc_18000992E
0x180009906  mov     eax, edi
0x180009908  lea     r8, ?s_bSingleBitMasks@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::s_bSingleBitMasks
0x18000990f  and     eax, 7
0x180009912  mov     ecx, edi
0x180009914  shr     rcx, 3
0x180009918  mov     al, [rax+r8]
0x18000991c  or      [rcx+rbx+18h], al
0x180009920  cmp     edi, 14h
0x180009923  jnb     short loc_18000992E
0x180009925  mov     [rbx+rdi*8+20h], rbp
0x18000992a  xor     eax, eax
0x18000992c  jmp     short loc_180009933
0x18000992e  mov     eax, 8000FFFFh
0x180009933  mov     rcx, [rsp+48h+var_20]
0x180009938  xor     rcx, rsp; StackCookie
0x18000993b  call    __security_check_cookie
0x180009940  mov     rbx, [rsp+48h+arg_10]
0x180009945  add     rsp, 30h
0x180009949  pop     rdi
0x18000994a  pop     rsi
0x18000994b  pop     rbp
0x18000994c  retn
```
