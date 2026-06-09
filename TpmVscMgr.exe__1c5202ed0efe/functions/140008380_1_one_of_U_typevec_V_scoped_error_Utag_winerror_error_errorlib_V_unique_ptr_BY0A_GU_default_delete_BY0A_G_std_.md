# ??1?$one_of@U?$typevec@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@Unil@typbldlib@@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@@typveclib@@U?$metavalue@$0A@@typbldlib@@U?$vec_size@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@Unil@typbldlib@@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@@detail@2@U34@@oneoflib@@QEAA@XZ

- ea: `0x140008380`
- end: `0x1400083b5`
- name: `??1?$one_of@U?$typevec@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@Unil@typbldlib@@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@@typveclib@@U?$metavalue@$0A@@typbldlib@@U?$vec_size@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@Unil@typbldlib@@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@@detail@2@U34@@oneoflib@@QEAA@XZ`
- size: `53`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140011b05`
- `0x140011d0d`
- `0x1400123a6`

## callees

- `0x140001934`
- `0x140008380`
- `0x140008454`

## pseudocode

```c
__int64 __fastcall __1__one_of_U__typevec_V__scoped_error_Utag_winerror_error___errorlib__V__unique_ptr___BY0A_GU__default_delete___BY0A_G_std___std__Unil_typbldlib__U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56__typveclib__U__metavalue__0A__typbldlib__U__vec_size_V__scoped_error_Utag_winerror_error___errorlib__V__unique_ptr___BY0A_GU__default_delete___BY0A_G_std___std__Unil_typbldlib__U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56__detail_2_U34__oneoflib__QEAA_XZ(
        __int64 a1,
        unsigned __int64 a2)
{
  _DWORD *v2; // rbx
  void *v3; // rcx
  __int64 result; // rax

  v2 = (_DWORD *)(a1 + 8);
  if ( *(_DWORD *)(a1 + 8) )
  {
    if ( *v2 == 1 )
    {
      v3 = *(void **)a1;
      if ( v3 )
        operator delete(v3, a2);
    }
  }
  else
  {
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(a1);
  }
  result = 2;
  *v2 = 2;
  return result;
}

```

## disassembly

```asm
0x140008380  push    rbx
0x140008382  sub     rsp, 20h
0x140008386  lea     rbx, [rcx+8]
0x14000838a  cmp     dword ptr [rbx], 0
0x14000838d  jnz     short loc_140008396
0x14000838f  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x140008394  jmp     short loc_1400083A8
0x140008396  cmp     dword ptr [rbx], 1
0x140008399  jnz     short loc_1400083A8
0x14000839b  mov     rcx, [rcx]; void *
0x14000839e  test    rcx, rcx
0x1400083a1  jz      short loc_1400083A8
0x1400083a3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400083a8  mov     eax, 2
0x1400083ad  mov     [rbx], eax
0x1400083af  add     rsp, 20h
0x1400083b3  pop     rbx
0x1400083b4  retn
```
