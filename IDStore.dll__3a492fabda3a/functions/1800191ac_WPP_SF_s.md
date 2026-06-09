# WPP_SF_s

- ea: `0x1800191ac`
- end: `0x180019209`
- name: `WPP_SF_s`
- size: `93`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `41`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001064`
- `0x180001230`
- `0x1800014fc`
- `0x180001808`
- `0x180001bf4`
- `0x180001c60`
- `0x180001d70`
- `0x180002030`
- `0x1800022d0`
- `0x180002500`
- `0x180002c80`
- `0x180003290`
- `0x180003560`
- `0x1800035f0`
- `0x1800037a0`
- `0x180003be0`
- `0x18000412c`
- `0x180004490`
- `0x180004e70`
- `0x180005000`
- `0x180005fe0`
- `0x180006260`
- `0x1800074dc`
- `0x180008260`
- `0x180008910`
- `0x180009cd0`
- `0x18000a120`
- `0x18000acb0`
- `0x18000ae70`
- `0x18000afb0`
- `0x18000b1c0`
- `0x18000b460`
- `0x18000b890`
- `0x18000be80`
- `0x18000c2a0`
- `0x18000c730`
- `0x18000cc10`
- `0x18000cef0`
- `0x18000d230`
- `0x18000d620`
- `0x18000e660`

## callees

- `0x1800191ac`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x1800191fe`
- `ntdll!EtwTraceMessage` at `0x1800191fe`

## pseudocode

```c
__int64 __fastcall WPP_SF_s(__int64 a1, unsigned __int16 a2, __int64 a3, const char *a4)
{
  __int64 v4; // rax
  __int64 v5; // rax

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = v4 + 1;
  }
  else
  {
    v5 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  return EtwTraceMessage(a1, 43, WPP_c5f3288c5351361fa7847b6cad0a7622_Traceguids, a2, a4, v5, 0);
}

```

## disassembly

```asm
0x1800191ac  sub     rsp, 48h
0x1800191b0  test    r9, r9
0x1800191b3  jz      short loc_1800191C8
0x1800191b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800191b9  inc     rax
0x1800191bc  cmp     byte ptr [r9+rax], 0
0x1800191c1  jnz     short loc_1800191B9
0x1800191c3  inc     rax
0x1800191c6  jmp     short loc_1800191CD
0x1800191c8  mov     eax, 5
0x1800191cd  test    r9, r9
0x1800191d0  mov     [rsp+48h+var_18], 0
0x1800191d9  lea     r8, aNull; "NULL"
0x1800191e0  mov     [rsp+48h+var_20], rax
0x1800191e5  cmovz   r9, r8
0x1800191e9  lea     r8, WPP_c5f3288c5351361fa7847b6cad0a7622_Traceguids
0x1800191f0  mov     [rsp+48h+var_28], r9
0x1800191f5  movzx   r9d, dx
0x1800191f9  mov     edx, 2Bh ; '+'
0x1800191fe  call    cs:__imp_EtwTraceMessage
0x180019204  add     rsp, 48h
0x180019208  retn
```
