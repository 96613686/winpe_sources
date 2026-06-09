# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000990c`
- end: `0x1800099c7`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800080f0`
- `0x180008b5c`
- `0x180011780`
- `0x180013094`

## callees

- `0x18000990c`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  __int64 v5; // r11
  unsigned __int16 *v6; // rax
  unsigned int v7; // edx
  __int64 v8; // rax
  __int64 v9; // r9
  unsigned __int16 *i; // rax
  unsigned __int16 *v11; // rcx

  v3 = 2147483646;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v5 = a2;
    v6 = a1;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v7 = v5 == 0 ? 0x80070057 : 0;
    v8 = (a2 - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      v9 = a2 - v8;
      for ( i = &a1[v8]; v9; --v9 )
      {
        if ( !v3 )
          break;
        if ( !*a3 )
          break;
        *i++ = *a3++;
        --v3;
      }
      v11 = i - 1;
      if ( v9 )
        v11 = i;
      v7 = v9 == 0 ? 0x8007007A : 0;
      *v11 = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000990c  mov     [rsp+arg_0], rbx
0x180009911  mov     [rsp+arg_8], rdi
0x180009916  lea     rax, [rdx-1]
0x18000991a  mov     r10d, 7FFFFFFEh
0x180009920  mov     r9, rdx
0x180009923  mov     rbx, rcx
0x180009926  cmp     rax, r10
0x180009929  ja      loc_1800099B5
0x18000992f  mov     r11, rdx
0x180009932  mov     rax, rcx
0x180009935  xor     edi, edi
0x180009937  cmp     [rax], di
0x18000993a  jz      short loc_180009946
0x18000993c  add     rax, 2
0x180009940  sub     r11, 1
0x180009944  jnz     short loc_180009937
0x180009946  mov     rax, r11
0x180009949  mov     rcx, r9
0x18000994c  neg     rax
0x18000994f  mov     rax, r11
0x180009952  sbb     edx, edx
0x180009954  sub     rcx, r11
0x180009957  not     edx
0x180009959  and     edx, 80070057h
0x18000995f  neg     rax
0x180009962  sbb     rax, rax
0x180009965  and     rax, rcx
0x180009968  test    r11, r11
0x18000996b  jz      short loc_1800099BA
0x18000996d  sub     r9, rax
0x180009970  lea     rax, [rbx+rax*2]
0x180009974  jz      short loc_180009998
0x180009976  test    r10, r10
0x180009979  jz      short loc_180009998
0x18000997b  movzx   ecx, word ptr [r8]
0x18000997f  test    cx, cx
0x180009982  jz      short loc_180009998
0x180009984  mov     [rax], cx
0x180009987  add     r8, 2
0x18000998b  add     rax, 2
0x18000998f  dec     r10
0x180009992  sub     r9, 1
0x180009996  jnz     short loc_180009976
0x180009998  test    r9, r9
0x18000999b  lea     rcx, [rax-2]
0x18000999f  cmovnz  rcx, rax
0x1800099a3  neg     r9
0x1800099a6  sbb     edx, edx
0x1800099a8  not     edx
0x1800099aa  and     edx, 8007007Ah
0x1800099b0  mov     [rcx], di
0x1800099b3  jmp     short loc_1800099BA
0x1800099b5  mov     edx, 80070057h
0x1800099ba  mov     rbx, [rsp+arg_0]
0x1800099bf  mov     eax, edx
0x1800099c1  mov     rdi, [rsp+arg_8]
0x1800099c6  retn
```
