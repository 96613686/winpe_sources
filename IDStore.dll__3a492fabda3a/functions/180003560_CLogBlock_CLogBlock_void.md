# CLogBlock::~CLogBlock(void)

- ea: `0x180003560`
- end: `0x1800035db`
- name: `??1CLogBlock@@QEAA@XZ`
- size: `123`
- prototype: `void __fastcall(CLogBlock *this, __int64, __int64)`
- caller_count: `45`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001064`
- `0x180001230`
- `0x1800014fc`
- `0x180001808`
- `0x180001bf4`
- `0x180001c60`
- `0x1800022d0`
- `0x180002500`
- `0x180002c80`
- `0x1800037a0`
- `0x18000412c`
- `0x1800074dc`
- `0x180008260`
- `0x180008910`
- `0x18000d620`
- `0x18000e660`
- `0x18000eb30`
- `0x180012b10`
- `0x1800130e0`
- `0x180013430`
- `0x180013b40`
- `0x1800140f0`
- `0x180014140`
- `0x1800146c0`
- `0x1800147a0`
- `0x180014de4`
- `0x180015184`
- `0x180015b30`
- `0x180015d10`
- `0x180016060`
- `0x180016400`
- `0x180016718`
- `0x180016bb8`
- `0x180016d1c`
- `0x180017328`
- `0x180018040`
- `0x180019870`
- `0x1800198c0`
- `0x1800198d2`
- `0x180019908`
- `0x180019920`
- `0x180019940`
- `0x180019a90`
- `0x180019b70`
- `0x18001a018`

## callees

- `0x180003560`
- `0x1800191ac`
- `0x180019210`

## pseudocode

```c
void __fastcall CLogBlock::~CLogBlock(CLogBlock *this, __int64 a2, __int64 a3)
{
  _DWORD *v3; // rax
  CIdentityProfileHandler *v5; // rcx

  v3 = *(_DWORD **)this;
  if ( !*(_QWORD *)this || (int)*v3 >= 0 )
    goto LABEL_3;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_sL(*((_QWORD *)WPP_GLOBAL_Control + 2), *v3, a3, *((_QWORD *)this + 1), *v3);
LABEL_3:
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x400) != 0 )
    WPP_SF_s(*((_QWORD *)v5 + 2), 12, a3, *((_QWORD *)this + 1));
}

```

## disassembly

```asm
0x180003560  mov     [rsp+arg_0], rbx
0x180003565  push    rdi
0x180003566  sub     rsp, 30h
0x18000356a  mov     rax, [rcx]
0x18000356d  lea     rdi, WPP_GLOBAL_Control
0x180003574  mov     rbx, rcx
0x180003577  test    rax, rax
0x18000357a  jz      short loc_180003582
0x18000357c  mov     edx, [rax]
0x18000357e  test    edx, edx
0x180003580  js      short loc_1800035A2
0x180003582  mov     rcx, cs:WPP_GLOBAL_Control
0x180003589  cmp     rcx, rdi
0x18000358c  jz      short loc_180003597
0x18000358e  test    dword ptr [rcx+1Ch], 400h
0x180003595  jnz     short loc_1800035C7
0x180003597  mov     rbx, [rsp+38h+arg_0]
0x18000359c  add     rsp, 30h
0x1800035a0  pop     rdi
0x1800035a1  retn
0x1800035a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035a9  cmp     rcx, rdi
0x1800035ac  jz      short loc_180003597
0x1800035ae  test    byte ptr [rcx+1Ch], 4
0x1800035b2  jz      short loc_180003589
0x1800035b4  mov     r9, [rbx+8]
0x1800035b8  mov     rcx, [rcx+10h]
0x1800035bc  mov     [rsp+38h+var_18], edx
0x1800035c0  call    WPP_SF_sL
0x1800035c5  jmp     short loc_180003582
0x1800035c7  mov     r9, [rbx+8]
0x1800035cb  mov     edx, 0Ch
0x1800035d0  mov     rcx, [rcx+10h]
0x1800035d4  call    WPP_SF_s
0x1800035d9  jmp     short loc_180003597
```
