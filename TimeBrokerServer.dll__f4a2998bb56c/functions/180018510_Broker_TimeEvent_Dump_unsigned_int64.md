# Broker::TimeEvent::Dump(unsigned __int64)

- ea: `0x180018510`
- end: `0x18001867e`
- name: `?Dump@TimeEvent@Broker@@UEAAX_K@Z`
- size: `366`
- prototype: `void __fastcall(Broker::TimeEvent *this, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180003800`
- `0x180009710`
- `0x180009fc0`
- `0x18000e5f0`
- `0x18001c010`

## pseudocode

```c
void __fastcall Broker::TimeEvent::Dump(Broker::TimeEvent *this, __int64 a2, __int64 a3)
{
  char v5; // al

  WPP_SF__guid_(a2, 25, a3, *((_QWORD *)this + 31));
  WPP_SF_S(a2, 26, &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids, *(_QWORD *)(*((_QWORD *)this + 31) + 24LL));
  WPP_SF_d(a2, 27, &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids, *((unsigned int *)this + 18));
  WPP_SF_i(a2, 28, &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids, *((_QWORD *)this + 6) / 600000000LL);
  WPP_SF_i(a2, 29, &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids, *((_QWORD *)this + 8) / 10000000LL);
  WPP_SF_i(a2, 30, &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids, *((_QWORD *)this + 3));
  WPP_SF_i(a2, 31, &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids, *((_QWORD *)this + 4));
  v5 = (*(__int64 (__fastcall **)(Broker::TimeEvent *))(*(_QWORD *)this + 48LL))(this);
  WPP_SF_d(a2, 32, &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids, v5 != 0);
  WPP_SF_i(a2, 33, &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids, *((_QWORD *)this + 7) / 10000000LL);
  WPP_SF_i(a2, 34, &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids, *((_QWORD *)this + 10) / 10000000LL);
}

```

## disassembly

```asm
0x180018510  push    rbx
0x180018512  push    rbp
0x180018513  push    rsi
0x180018514  push    rdi
0x180018515  sub     rsp, 28h
0x180018519  mov     rdi, rdx
0x18001851c  mov     rbx, rcx
0x18001851f  mov     r9, [rcx+0F8h]
0x180018526  mov     edx, 19h
0x18001852b  mov     rcx, rdi
0x18001852e  call    WPP_SF__guid_
0x180018533  mov     r9, [rbx+0F8h]
0x18001853a  lea     rbp, WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids
0x180018541  mov     edx, 1Ah
0x180018546  mov     r8, rbp
0x180018549  mov     rcx, rdi
0x18001854c  mov     r9, [r9+18h]
0x180018550  call    WPP_SF_S
0x180018555  mov     r9d, [rbx+48h]
0x180018559  mov     edx, 1Bh
0x18001855e  mov     r8, rbp
0x180018561  mov     rcx, rdi
0x180018564  call    WPP_SF_d
0x180018569  mov     rax, 1CA213D840BAF7D5h
0x180018573  mov     r8, rbp
0x180018576  imul    qword ptr [rbx+30h]
0x18001857a  mov     rcx, rdi
0x18001857d  mov     r9, rdx
0x180018580  mov     edx, 1Ch
0x180018585  sar     r9, 1Ah
0x180018589  mov     rax, r9
0x18001858c  shr     rax, 3Fh
0x180018590  add     r9, rax
0x180018593  call    WPP_SF_i
0x180018598  mov     rsi, 0D6BF94D5E57A42BDh
0x1800185a2  mov     r8, rbp
0x1800185a5  mov     rax, rsi
0x1800185a8  mov     rcx, rdi
0x1800185ab  imul    qword ptr [rbx+40h]
0x1800185af  mov     r9, rdx
0x1800185b2  mov     edx, 1Dh
0x1800185b7  add     r9, [rbx+40h]
0x1800185bb  sar     r9, 17h
0x1800185bf  mov     rax, r9
0x1800185c2  shr     rax, 3Fh
0x1800185c6  add     r9, rax
0x1800185c9  call    WPP_SF_i
0x1800185ce  mov     r9, [rbx+18h]
0x1800185d2  mov     edx, 1Eh
0x1800185d7  mov     r8, rbp
0x1800185da  mov     rcx, rdi
0x1800185dd  call    WPP_SF_i
0x1800185e2  mov     r9, [rbx+20h]
0x1800185e6  mov     edx, 1Fh
0x1800185eb  mov     r8, rbp
0x1800185ee  mov     rcx, rdi
0x1800185f1  call    WPP_SF_i
0x1800185f6  mov     rax, [rbx]
0x1800185f9  mov     rcx, rbx
0x1800185fc  mov     rax, [rax+30h]
0x180018600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018605  xor     r9d, r9d
0x180018608  mov     edx, 20h ; ' '
0x18001860d  test    al, al
0x18001860f  mov     r8, rbp
0x180018612  mov     rcx, rdi
0x180018615  setnz   r9b
0x180018619  call    WPP_SF_d
0x18001861e  mov     rax, rsi
0x180018621  mov     r8, rbp
0x180018624  imul    qword ptr [rbx+38h]
0x180018628  mov     r9, rdx
0x18001862b  mov     edx, 21h ; '!'
0x180018630  add     r9, [rbx+38h]
0x180018634  sar     r9, 17h
0x180018638  mov     rcx, r9
0x18001863b  shr     rcx, 3Fh
0x18001863f  add     r9, rcx
0x180018642  mov     rcx, rdi
0x180018645  call    WPP_SF_i
0x18001864a  mov     rax, rsi
0x18001864d  mov     r8, rbp
0x180018650  imul    qword ptr [rbx+50h]
0x180018654  mov     rcx, rdi
0x180018657  mov     r9, rdx
0x18001865a  mov     edx, 22h ; '"'
0x18001865f  add     r9, [rbx+50h]
0x180018663  sar     r9, 17h
0x180018667  mov     rax, r9
0x18001866a  shr     rax, 3Fh
0x18001866e  add     r9, rax
0x180018671  add     rsp, 28h
0x180018675  pop     rdi
0x180018676  pop     rsi
0x180018677  pop     rbp
0x180018678  pop     rbx
0x180018679  jmp     WPP_SF_i
```
