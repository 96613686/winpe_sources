# LpcVerifyOutgoingPayloadSize(_PORT_MESSAGE const *)

- ea: `0x1400025f0`
- end: `0x140002620`
- name: `?LpcVerifyOutgoingPayloadSize@@YAXPEBU_PORT_MESSAGE@@@Z`
- size: `48`
- prototype: `void __fastcall(const struct _PORT_MESSAGE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002518`

## callees

- `0x1400025f0`
- `0x14000daa4`

## string_xrefs

- `0x140002604`: `onecoreuap\windows\DWM\common\shared\lpcshared.h`

## pseudocode

```c
void __fastcall LpcVerifyOutgoingPayloadSize(const struct _PORT_MESSAGE *a1)
{
  int v1; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a1->u1.s1.TotalLength > 512 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x148,
      (unsigned int)"onecoreuap\\windows\\DWM\\common\\shared\\lpcshared.h",
      (const char *)0x8007029CLL,
      v1);
}

```

## disassembly

```asm
0x1400025f0  sub     rsp, 28h
0x1400025f4  mov     eax, 200h
0x1400025f9  cmp     [rcx+2], ax
0x1400025fd  jle     short loc_14000261B
0x1400025ff  mov     rcx, [rsp+28h]; this
0x140002604  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\DWM\\common\\share"...
0x14000260b  mov     r9d, 8007029Ch; char *
0x140002611  mov     edx, 148h; void *
0x140002616  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x14000261b  add     rsp, 28h
0x14000261f  retn
```
