# _Trace::~_Trace(void)

- ea: `0x14000c2bc`
- end: `0x14000c338`
- name: `??1_Trace@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(_Trace *__hidden this)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d498`
- `0x14000ea38`
- `0x14000f9c0`
- `0x14000fd08`
- `0x140010e44`
- `0x140015d72`
- `0x140015e26`
- `0x140015e92`
- `0x140015f10`

## callees

- `0x14000abd8`
- `0x14000c2bc`
- `0x14000cc64`

## pseudocode

```c
void __fastcall _Trace::~_Trace(_Trace *this, __int64 a2, int a3)
{
  _DWORD *v4; // rax
  _QWORD *v5; // rcx

  v4 = *(_DWORD **)this;
  if ( !*(_QWORD *)this || (int)*v4 >= 0 )
    goto LABEL_6;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_SL(*((_QWORD *)WPP_GLOBAL_Control + 2), *v4, a3, *((_QWORD *)this + 1), *v4);
LABEL_6:
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x40) != 0 )
    WPP_SF_S(v5[2], 12, &WPP_4fe2a7da30c630366b37eac893510770_Traceguids, *((_QWORD *)this + 1));
}

```

## disassembly

```asm
0x14000c2bc  mov     [rsp+arg_0], rbx
0x14000c2c1  push    rdi
0x14000c2c2  sub     rsp, 30h
0x14000c2c6  mov     rbx, rcx
0x14000c2c9  mov     rax, [rcx]
0x14000c2cc  lea     rdi, WPP_GLOBAL_Control
0x14000c2d3  test    rax, rax
0x14000c2d6  jz      short loc_14000C301
0x14000c2d8  mov     edx, [rax]
0x14000c2da  test    edx, edx
0x14000c2dc  jns     short loc_14000C301
0x14000c2de  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c2e5  cmp     rcx, rdi
0x14000c2e8  jz      short loc_14000C32D
0x14000c2ea  test    byte ptr [rcx+1Ch], 4
0x14000c2ee  jz      short loc_14000C308
0x14000c2f0  mov     [rsp+38h+var_18], edx
0x14000c2f4  mov     r9, [rbx+8]
0x14000c2f8  mov     rcx, [rcx+10h]
0x14000c2fc  call    WPP_SF_SL
0x14000c301  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c308  cmp     rcx, rdi
0x14000c30b  jz      short loc_14000C32D
0x14000c30d  test    byte ptr [rcx+1Ch], 40h
0x14000c311  jz      short loc_14000C32D
0x14000c313  mov     edx, 0Ch
0x14000c318  mov     r9, [rbx+8]
0x14000c31c  lea     r8, WPP_4fe2a7da30c630366b37eac893510770_Traceguids
0x14000c323  mov     rcx, [rcx+10h]
0x14000c327  call    WPP_SF_S
0x14000c32c  nop
0x14000c32d  mov     rbx, [rsp+38h+arg_0]
0x14000c332  add     rsp, 30h
0x14000c336  pop     rdi
0x14000c337  retn
```
