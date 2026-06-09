# HttpApiTerminateConfiguration

- ea: `0x18000750c`
- end: `0x18000758e`
- name: `HttpApiTerminateConfiguration`
- size: `130`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800034a0`
- `0x180003ad0`

## callees

- `0x180003aa0`
- `0x18000750c`
- `0x18000bdd0`
- `0x18000be2c`

## pseudocode

```c
__int64 __fastcall HttpApiTerminateConfiguration(__int64 a1, __int64 a2, __int64 a3)
{
  char v3; // di
  unsigned int v4; // ebx

  v3 = a1;
  v4 = 87;
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_L(a1, 22, WPP_d1f5b049c58935796a293ebb03e09278_Traceguids);
  if ( (v3 & 2) != 0 )
  {
    if ( dword_18001276C )
    {
      v4 = 0;
      if ( dword_18001276C == 1 )
      {
        TerminateConfigurationGlobals();
        dword_18001276C = 0;
      }
      else
      {
        --dword_18001276C;
      }
    }
    else
    {
      v4 = 1114;
    }
  }
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_Dd(a1, 23, a3, v4);
  return v4;
}

```

## disassembly

```asm
0x18000750c  mov     [rsp+arg_0], rbx
0x180007511  push    rdi
0x180007512  sub     rsp, 30h
0x180007516  mov     edi, ecx
0x180007518  mov     ebx, 57h ; 'W'
0x18000751d  test    cs:byte_1800126A3, 4
0x180007524  jz      short loc_180007538
0x180007526  lea     edx, [rbx-41h]
0x180007529  mov     r9d, ecx
0x18000752c  lea     r8, WPP_d1f5b049c58935796a293ebb03e09278_Traceguids
0x180007533  call    WPP_SF_L
0x180007538  test    dil, 2
0x18000753c  jz      short loc_18000756B
0x18000753e  mov     eax, cs:dword_18001276C
0x180007544  test    eax, eax
0x180007546  jnz     short loc_18000754F
0x180007548  mov     ebx, 45Ah
0x18000754d  jmp     short loc_18000756B
0x18000754f  xor     ebx, ebx
0x180007551  cmp     eax, 1
0x180007554  jnz     short loc_180007563
0x180007556  call    TerminateConfigurationGlobals
0x18000755b  mov     cs:dword_18001276C, ebx
0x180007561  jmp     short loc_18000756B
0x180007563  dec     eax
0x180007565  mov     cs:dword_18001276C, eax
0x18000756b  test    cs:byte_1800126A3, 4
0x180007572  jz      short loc_180007581
0x180007574  mov     edx, 17h
0x180007579  mov     r9d, ebx
0x18000757c  call    WPP_SF_Dd
0x180007581  mov     eax, ebx
0x180007583  mov     rbx, [rsp+38h+arg_0]
0x180007588  add     rsp, 30h
0x18000758c  pop     rdi
0x18000758d  retn
```
