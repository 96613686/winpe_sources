# _ParseCreateParams_::_1_::dtor$80

- ea: `0x1400123a6`
- end: `0x1400123b2`
- name: `_ParseCreateParams_::_1_::dtor$80`
- size: `12`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140008380`

## pseudocode

```c
__int64 __fastcall ParseCreateParams_::_1_::dtor_80(__int64 a1, unsigned __int64 a2)
{
  return __1__one_of_U__typevec_V__scoped_error_Utag_winerror_error___errorlib__V__unique_ptr___BY0A_GU__default_delete___BY0A_G_std___std__Unil_typbldlib__U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56__typveclib__U__metavalue__0A__typbldlib__U__vec_size_V__scoped_error_Utag_winerror_error___errorlib__V__unique_ptr___BY0A_GU__default_delete___BY0A_G_std___std__Unil_typbldlib__U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56_U56__detail_2_U34__oneoflib__QEAA_XZ(
           a2 + 248,
           a2);
}

```

## disassembly

```asm
0x1400123a6  lea     rcx, [rdx+0F8h]
0x1400123ad  jmp     ??1?$one_of@U?$typevec@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@Unil@typbldlib@@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@@typveclib@@U?$metavalue@$0A@@typbldlib@@U?$vec_size@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@Unil@typbldlib@@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@@detail@2@U34@@oneoflib@@QEAA@XZ
```
