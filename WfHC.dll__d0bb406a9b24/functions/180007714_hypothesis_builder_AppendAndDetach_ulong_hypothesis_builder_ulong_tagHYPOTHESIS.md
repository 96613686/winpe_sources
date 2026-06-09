# _hypothesis_builder::AppendAndDetach(ulong,_hypothesis_builder *,ulong *,tagHYPOTHESIS * *)

- ea: `0x180007714`
- end: `0x1800078a6`
- name: `?AppendAndDetach@_hypothesis_builder@@QEAAJKPEAV1@PEAKPEAPEAUtagHYPOTHESIS@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(_hypothesis_builder *this, unsigned int, struct _hypothesis_builder *, unsigned int *, struct tagHYPOTHESIS **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002c10`

## callees

- `0x180007714`
- `0x1800078ac`
- `0x180007958`
- `0x18000c168`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000777a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000785a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000777a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000785a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800077d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800077d1`

## pseudocode

```c
__int64 __fastcall _hypothesis_builder::AppendAndDetach(
        _hypothesis_builder *this,
        unsigned int a2,
        struct _hypothesis_builder *a3,
        unsigned int *a4,
        struct tagHYPOTHESIS **a5)
{
  struct tagHYPOTHESIS **v5; // r12
  unsigned int v6; // r14d
  __int64 result; // rax
  SIZE_T v12; // rsi
  struct tagHYPOTHESIS *v13; // rax
  struct tagHYPOTHESIS *v14; // rdi
  int v15; // ebx
  unsigned int v16; // esi
  struct tagHYPOTHESIS *v17; // rbx
  __int64 v18; // rdi
  _BYTE *v19; // rax
  unsigned int v20[22]; // [rsp+20h] [rbp-58h] BYREF

  v5 = a5;
  v6 = 0;
  if ( !a5 || !a4 )
    return 2147942487LL;
  if ( a2 )
  {
    if ( a3 )
    {
      if ( a2 > 0x7FFFFFE )
        return 2147942934LL;
      v12 = 32LL * (a2 + 1);
      v13 = (struct tagHYPOTHESIS *)CoTaskMemAlloc(v12);
      v14 = v13;
      if ( !v13 )
        return 2147942414LL;
      for ( ; v12; --v12 )
      {
        LOBYTE(v13->pwszClassName) = 0;
        v13 = (struct tagHYPOTHESIS *)((char *)v13 + 1);
      }
      v20[0] = 0;
      LODWORD(a5) = 0;
      v15 = _hypothesis_builder::DetachInPlace(this, v14, (unsigned int *)&a5, v20);
      if ( v15 >= 0 )
      {
        v16 = (unsigned int)a5;
        v17 = (struct tagHYPOTHESIS *)((char *)v14 + v20[0]);
        if ( a2 )
        {
          do
          {
            if ( (int)_hypothesis_builder::DetachInPlace(
                        (struct _hypothesis_builder *)((char *)a3 + 40 * v6),
                        v17,
                        (unsigned int *)&a5,
                        v20) < 0 )
              break;
            ++v6;
            v16 += (unsigned int)a5;
            v17 = (struct tagHYPOTHESIS *)((char *)v17 + v20[0]);
          }
          while ( v6 < a2 );
        }
        *v5 = v14;
        result = 0;
        *a4 = v16;
      }
      else
      {
        CoTaskMemFree(v14);
        return (unsigned int)v15;
      }
      return result;
    }
    return 2147942487LL;
  }
  if ( !*((_QWORD *)this + 4) )
  {
    if ( *((_DWORD *)this + 4) || *((_QWORD *)this + 3) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v18 = 32;
    v19 = CoTaskMemAlloc(0x20u);
    *((_QWORD *)this + 4) = v19;
    if ( !v19 )
      return 2147942414LL;
    do
    {
      *v19++ = 0;
      --v18;
    }
    while ( v18 );
  }
  _hypothesis_builder::DoDetach(this, v5);
  result = 0;
  *a4 = 1;
  return result;
}

```

## disassembly

```asm
0x180007714  push    rbx
0x180007716  push    rbp
0x180007717  push    rsi
0x180007718  push    rdi
0x180007719  push    r12
0x18000771b  push    r13
0x18000771d  push    r14
0x18000771f  push    r15
0x180007721  sub     rsp, 38h
0x180007725  mov     r12, [rsp+78h+arg_20]
0x18000772d  xor     r14d, r14d
0x180007730  mov     r15, r9
0x180007733  mov     r13, r8
0x180007736  mov     ebp, edx
0x180007738  mov     rbx, rcx
0x18000773b  test    r12, r12
0x18000773e  jz      loc_180007890
0x180007744  test    r9, r9
0x180007747  jz      loc_180007890
0x18000774d  test    edx, edx
0x18000774f  jz      loc_18000783C
0x180007755  test    r8, r8
0x180007758  jz      loc_180007890
0x18000775e  cmp     edx, 7FFFFFEh
0x180007764  jbe     short loc_180007770
0x180007766  mov     eax, 80070216h
0x18000776b  jmp     loc_180007895
0x180007770  lea     esi, [rdx+1]
0x180007773  shl     rsi, 5
0x180007777  mov     rcx, rsi; cb
0x18000777a  call    cs:__imp_CoTaskMemAlloc
0x180007780  mov     rdi, rax
0x180007783  test    rax, rax
0x180007786  jnz     short loc_180007792
0x180007788  mov     eax, 8007000Eh
0x18000778d  jmp     loc_180007895
0x180007792  test    rsi, rsi
0x180007795  jz      short loc_1800077A3
0x180007797  mov     [rax], r14b
0x18000779a  inc     rax
0x18000779d  sub     rsi, 1
0x1800077a1  jnz     short loc_180007797
0x1800077a3  lea     r9, [rsp+78h+var_58]; unsigned int *
0x1800077a8  mov     [rsp+78h+var_58], r14d
0x1800077ad  lea     r8, [rsp+78h+arg_20]; unsigned int *
0x1800077b5  mov     dword ptr [rsp+78h+arg_20], r14d
0x1800077bd  mov     rdx, rdi; struct tagHYPOTHESIS *
0x1800077c0  mov     rcx, rbx; this
0x1800077c3  call    ?DetachInPlace@_hypothesis_builder@@IEAAJAEAUtagHYPOTHESIS@@PEAK1@Z; _hypothesis_builder::DetachInPlace(tagHYPOTHESIS &,ulong *,ulong *)
0x1800077c8  mov     ebx, eax
0x1800077ca  test    eax, eax
0x1800077cc  jns     short loc_1800077DE
0x1800077ce  mov     rcx, rdi; pv
0x1800077d1  call    cs:__imp_CoTaskMemFree
0x1800077d7  mov     eax, ebx
0x1800077d9  jmp     loc_180007895
0x1800077de  mov     ebx, [rsp+78h+var_58]
0x1800077e2  mov     esi, dword ptr [rsp+78h+arg_20]
0x1800077e9  add     rbx, rdi
0x1800077ec  test    ebp, ebp
0x1800077ee  jz      short loc_180007831
0x1800077f0  mov     eax, r14d
0x1800077f3  lea     r9, [rsp+78h+var_58]; unsigned int *
0x1800077f8  lea     r8, [rsp+78h+arg_20]; unsigned int *
0x180007800  mov     rdx, rbx; struct tagHYPOTHESIS *
0x180007803  lea     rcx, [rax+rax*4]
0x180007807  lea     rcx, ds:0[rcx*8]
0x18000780f  add     rcx, r13; this
0x180007812  call    ?DetachInPlace@_hypothesis_builder@@IEAAJAEAUtagHYPOTHESIS@@PEAK1@Z; _hypothesis_builder::DetachInPlace(tagHYPOTHESIS &,ulong *,ulong *)
0x180007817  test    eax, eax
0x180007819  js      short loc_180007831
0x18000781b  mov     eax, [rsp+78h+var_58]
0x18000781f  inc     r14d
0x180007822  add     esi, dword ptr [rsp+78h+arg_20]
0x180007829  add     rbx, rax
0x18000782c  cmp     r14d, ebp
0x18000782f  jb      short loc_1800077F0
0x180007831  mov     [r12], rdi
0x180007835  xor     eax, eax
0x180007837  mov     [r15], esi
0x18000783a  jmp     short loc_180007895
0x18000783c  cmp     [rcx+20h], r14
0x180007840  jnz     short loc_180007879
0x180007842  cmp     [rcx+10h], r14d
0x180007846  jnz     short loc_18000784E
0x180007848  cmp     [rcx+18h], r14
0x18000784c  jz      short loc_180007853
0x18000784e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007853  mov     edi, 20h ; ' '
0x180007858  mov     ecx, edi; cb
0x18000785a  call    cs:__imp_CoTaskMemAlloc
0x180007860  mov     [rbx+20h], rax
0x180007864  test    rax, rax
0x180007867  jz      loc_180007788
0x18000786d  mov     [rax], r14b
0x180007870  inc     rax
0x180007873  sub     rdi, 1
0x180007877  jnz     short loc_18000786D
0x180007879  mov     rdx, r12; struct tagHYPOTHESIS **
0x18000787c  mov     rcx, rbx; this
0x18000787f  call    ?DoDetach@_hypothesis_builder@@IEAAXPEAPEAUtagHYPOTHESIS@@@Z; _hypothesis_builder::DoDetach(tagHYPOTHESIS * *)
0x180007884  mov     eax, r14d
0x180007887  mov     dword ptr [r15], 1
0x18000788e  jmp     short loc_180007895
0x180007890  mov     eax, 80070057h
0x180007895  add     rsp, 38h
0x180007899  pop     r15
0x18000789b  pop     r14
0x18000789d  pop     r13
0x18000789f  pop     r12
0x1800078a1  pop     rdi
0x1800078a2  pop     rsi
0x1800078a3  pop     rbp
0x1800078a4  pop     rbx
0x1800078a5  retn
```
