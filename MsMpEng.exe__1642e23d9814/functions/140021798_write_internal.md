# _write_internal

- ea: `0x140021798`
- end: `0x1400218b5`
- name: `_write_internal`
- size: `285`
- prototype: `__int64 __fastcall(int, __int64, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14001c13c`
- `0x140021700`

## callees

- `0x140015fe4`
- `0x14001e450`
- `0x14001e538`
- `0x140021798`
- `0x1400218b8`

## pseudocode

```c
__int64 __fastcall write_internal(int a1, __int64 a2, unsigned int a3, __int64 a4)
{
  BOOL v8; // eax
  __int64 v9; // r15
  unsigned int v10; // r14d

  if ( a1 == -2 )
  {
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    return 0xFFFFFFFFLL;
  }
  v8 = a1 >= 0 && a1 < (unsigned int)dword_14003EA00;
  if ( !v8 || (v9 = (__int64)a1 >> 6, (*(_BYTE *)(qword_14003E600[v9] + 72LL * (a1 & 0x3F) + 56) & 1) == 0) )
  {
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    sub_140015FE4(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)a4);
    return 0xFFFFFFFFLL;
  }
  _acrt_lowio_lock_fh((unsigned int)a1);
  v10 = -1;
  if ( (*(_BYTE *)(qword_14003E600[v9] + 72LL * (a1 & 0x3F) + 56) & 1) != 0 )
  {
    v10 = sub_1400218B8((unsigned int)a1, a2, a3, a4);
  }
  else
  {
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
  }
  _acrt_lowio_unlock_fh(a1);
  return v10;
}

```

## disassembly

```asm
0x140021798  mov     [rsp+arg_10], rbx
0x14002179d  mov     [rsp+arg_8], rdx
0x1400217a2  mov     [rsp+arg_0], ecx
0x1400217a6  push    rsi
0x1400217a7  push    r12
0x1400217a9  push    r13
0x1400217ab  push    r14
0x1400217ad  push    r15
0x1400217af  sub     rsp, 30h
0x1400217b3  mov     rbx, r9
0x1400217b6  mov     r13d, r8d
0x1400217b9  movsxd  rsi, ecx
0x1400217bc  cmp     esi, 0FFFFFFFEh
0x1400217bf  jnz     short loc_1400217EE
0x1400217c1  mov     byte ptr [r9+38h], 1
0x1400217c6  and     dword ptr [r9+34h], 0
0x1400217cb  mov     byte ptr [r9+30h], 1
0x1400217d0  mov     dword ptr [r9+2Ch], 9
0x1400217d8  or      eax, 0FFFFFFFFh
0x1400217db  mov     rbx, [rsp+58h+arg_10]
0x1400217e0  add     rsp, 30h
0x1400217e4  pop     r15
0x1400217e6  pop     r14
0x1400217e8  pop     r13
0x1400217ea  pop     r12
0x1400217ec  pop     rsi
0x1400217ed  retn
0x1400217ee  test    ecx, ecx
0x1400217f0  js      short loc_140021801
0x1400217f2  cmp     esi, cs:dword_14003EA00
0x1400217f8  jnb     short loc_140021801
0x1400217fa  mov     eax, 1
0x1400217ff  jmp     short loc_140021803
0x140021801  xor     eax, eax
0x140021803  test    eax, eax
0x140021805  jnz     short loc_14002183A
0x140021807  mov     byte ptr [r9+38h], 1
0x14002180c  and     dword ptr [r9+34h], 0
0x140021811  mov     byte ptr [r9+30h], 1
0x140021816  mov     dword ptr [r9+2Ch], 9
0x14002181e  mov     [rsp+58h+var_30], rbx; __crt_cached_ptd_host *
0x140021823  and     [rsp+58h+var_38], 0
0x140021829  xor     r9d, r9d; LineNo
0x14002182c  xor     r8d, r8d; FileName
0x14002182f  xor     edx, edx; FunctionName
0x140021831  xor     ecx, ecx; Expression
0x140021833  call    sub_140015FE4
0x140021838  jmp     short loc_1400217D8
0x14002183a  mov     rax, rsi
0x14002183d  mov     r15, rsi
0x140021840  sar     r15, 6
0x140021844  lea     rcx, qword_14003E600
0x14002184b  and     eax, 3Fh
0x14002184e  lea     r12, [rax+rax*8]
0x140021852  mov     rax, [rcx+r15*8]
0x140021856  test    byte ptr [rax+r12*8+38h], 1
0x14002185c  jz      short loc_140021807
0x14002185e  mov     ecx, esi
0x140021860  call    __acrt_lowio_lock_fh
0x140021865  or      r14d, 0FFFFFFFFh
0x140021869  lea     rax, qword_14003E600
0x140021870  mov     rax, [rax+r15*8]
0x140021874  test    byte ptr [rax+r12*8+38h], 1
0x14002187a  jnz     short loc_140021891
0x14002187c  mov     byte ptr [rbx+30h], 1
0x140021880  mov     dword ptr [rbx+2Ch], 9
0x140021887  mov     byte ptr [rbx+38h], 1
0x14002188b  and     dword ptr [rbx+34h], 0
0x14002188f  jmp     short loc_1400218A6
0x140021891  mov     r9, rbx
0x140021894  mov     r8d, r13d
0x140021897  mov     rdx, [rsp+58h+arg_8]
0x14002189c  mov     ecx, esi
0x14002189e  call    sub_1400218B8
0x1400218a3  mov     r14d, eax
0x1400218a6  mov     ecx, esi
0x1400218a8  call    __acrt_lowio_unlock_fh
0x1400218ad  mov     eax, r14d
0x1400218b0  jmp     loc_1400217DB
0x14002b231  push    rbp; Microsoft VisualC 64bit universal runtime
0x14002b233  sub     rsp, 30h
0x14002b237  mov     rbp, rdx
0x14002b23a  mov     ecx, [rbp+60h]
0x14002b23d  add     rsp, 30h
0x14002b241  pop     rbp
0x14002b242  jmp     __acrt_lowio_unlock_fh
```
