# Apx::ApfVerify::ValidateString(ushort const *)

- ea: `0x18000aea8`
- end: `0x18000af2b`
- name: `?ValidateString@ApfVerify@Apx@@YAJPEBG@Z`
- size: `131`
- prototype: `__int64 __fastcall(Apx::ApfVerify *__hidden this, const unsigned __int16 *)`
- caller_count: `27`
- callee_count: `2`
- tags: ``

## callers

- `0x1800208ec`
- `0x180020b80`
- `0x180020d60`
- `0x180020e30`
- `0x180020f00`
- `0x180020fd0`
- `0x1800210a0`
- `0x180021170`
- `0x180021350`
- `0x180021420`
- `0x1800215d0`
- `0x1800216a0`
- `0x180021770`
- `0x180021840`
- `0x180021910`
- `0x180021aa0`
- `0x180021b80`
- `0x180021c60`
- `0x180021d40`
- `0x180021e20`
- `0x180021f00`
- `0x180022090`
- `0x180022170`
- `0x180022300`
- `0x1800223e0`
- `0x1800224c0`
- `0x1800225a0`

## callees

- `0x18000aea8`
- `0x18000af34`

## pseudocode

```c
__int64 __fastcall Apx::ApfVerify::ValidateString(Apx::ApfVerify *this, const unsigned __int16 *a2)
{
  __int64 v2; // rdx
  Apx::ApfVerify *v3; // rax
  unsigned int v4; // ebx

  if ( !this )
  {
    v4 = -2147024809;
LABEL_8:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)WPP_3636aa9f48713a73a6db16bd0dcceb8b_Traceguids,
        (_DWORD)this,
        v4);
    }
    return v4;
  }
  v2 = 260;
  v3 = this;
  do
  {
    if ( !*(_WORD *)v3 )
      break;
    v3 = (Apx::ApfVerify *)((char *)v3 + 2);
    --v2;
  }
  while ( v2 );
  v4 = v2 == 0 ? 0x80070057 : 0;
  if ( !v2 )
    goto LABEL_8;
  return v4;
}

```

## disassembly

```asm
0x18000aea8  push    rbx
0x18000aeaa  sub     rsp, 30h
0x18000aeae  mov     r9, rcx
0x18000aeb1  xor     ecx, ecx
0x18000aeb3  test    r9, r9
0x18000aeb6  jz      short loc_18000AEE6
0x18000aeb8  mov     edx, 104h
0x18000aebd  mov     rax, r9
0x18000aec0  cmp     [rax], cx
0x18000aec3  jz      short loc_18000AECF
0x18000aec5  add     rax, 2
0x18000aec9  sub     rdx, 1
0x18000aecd  jnz     short loc_18000AEC0
0x18000aecf  mov     rax, rdx
0x18000aed2  neg     rax
0x18000aed5  sbb     ebx, ebx
0x18000aed7  not     ebx
0x18000aed9  and     ebx, 80070057h
0x18000aedf  test    rdx, rdx
0x18000aee2  jnz     short loc_18000AF23
0x18000aee4  jmp     short loc_18000AEEB
0x18000aee6  mov     ebx, 80070057h
0x18000aeeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aef2  lea     rax, WPP_GLOBAL_Control
0x18000aef9  cmp     rcx, rax
0x18000aefc  jz      short loc_18000AF23
0x18000aefe  test    byte ptr [rcx+1Ch], 40h
0x18000af02  jz      short loc_18000AF23
0x18000af04  cmp     byte ptr [rcx+19h], 2
0x18000af08  jb      short loc_18000AF23
0x18000af0a  mov     rcx, [rcx+10h]
0x18000af0e  lea     r8, WPP_3636aa9f48713a73a6db16bd0dcceb8b_Traceguids
0x18000af15  mov     edx, 13h
0x18000af1a  mov     [rsp+38h+var_18], ebx
0x18000af1e  call    WPP_SF_Sd
0x18000af23  mov     eax, ebx
0x18000af25  add     rsp, 30h
0x18000af29  pop     rbx
0x18000af2a  retn
```
