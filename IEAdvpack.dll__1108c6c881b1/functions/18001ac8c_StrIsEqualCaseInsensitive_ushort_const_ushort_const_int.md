# StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)

- ea: `0x18001ac8c`
- end: `0x18001acde`
- name: `?StrIsEqualCaseInsensitive@@YA_NPEBG0H@Z`
- size: `82`
- prototype: `bool __fastcall(const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180019fb8`
- `0x18001a688`
- `0x18001a720`
- `0x18001b524`

## callees

- `0x18001ac8c`

## pseudocode

```c
bool __fastcall StrIsEqualCaseInsensitive(const unsigned __int16 *a1, const unsigned __int16 *a2, int a3)
{
  int v5; // r9d
  int v6; // edx
  int v7; // r10d
  int v8; // ecx

  do
  {
    v5 = *a1;
    v6 = *a2;
    v7 = v5 + 32;
    if ( (unsigned int)(v5 - 65) > 0x19 )
      v7 = *a1;
    v8 = v6 + 32;
    if ( (unsigned int)(v6 - 65) > 0x19 )
      v8 = *a2;
    if ( !--a3 )
      break;
    if ( !v7 )
      break;
    ++a1;
    ++a2;
  }
  while ( v7 == v8 );
  return v7 == v8;
}

```

## disassembly

```asm
0x18001ac8c  mov     [rsp+arg_0], rbx
0x18001ac91  mov     r11, rdx
0x18001ac94  mov     rbx, rcx
0x18001ac97  movzx   r9d, word ptr [rbx]
0x18001ac9b  movzx   edx, word ptr [r11]
0x18001ac9f  lea     eax, [r9-41h]
0x18001aca3  cmp     eax, 19h
0x18001aca6  lea     r10d, [r9+20h]
0x18001acaa  lea     eax, [rdx-41h]
0x18001acad  cmova   r10d, r9d
0x18001acb1  lea     ecx, [rdx+20h]
0x18001acb4  cmp     eax, 19h
0x18001acb7  cmova   ecx, edx
0x18001acba  sub     r8d, 1
0x18001acbe  jz      short loc_18001ACD2
0x18001acc0  test    r10d, r10d
0x18001acc3  jz      short loc_18001ACD2
0x18001acc5  add     rbx, 2
0x18001acc9  add     r11, 2
0x18001accd  cmp     r10d, ecx
0x18001acd0  jz      short loc_18001AC97
0x18001acd2  mov     rbx, [rsp+arg_0]
0x18001acd7  cmp     r10d, ecx
0x18001acda  setz    al
0x18001acdd  retn
```
