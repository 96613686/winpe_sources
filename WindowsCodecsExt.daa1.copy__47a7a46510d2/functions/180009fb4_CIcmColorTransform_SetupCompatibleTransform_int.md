# CIcmColorTransform::SetupCompatibleTransform(int *)

- ea: `0x180009fb4`
- end: `0x18000a197`
- name: `?SetupCompatibleTransform@CIcmColorTransform@@IEAAJPEAH@Z`
- size: `483`
- prototype: `__int64 __fastcall(CIcmColorTransform *__hidden this, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009bb0`

## callees

- `0x180009fb4`
- `0x18000a1a0`
- `0x18000b5f0`
- `0x18000bcc0`
- `0x1800171c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a0ef`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a14b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a0ef`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a14b`

## pseudocode

```c
__int64 __fastcall CIcmColorTransform::SetupCompatibleTransform(CIcmColorTransform *this, int *a2)
{
  unsigned int v2; // r9d
  unsigned int v4; // esi
  unsigned int v6; // ebp
  HRESULT v7; // eax
  unsigned int v8; // ebx
  int v10; // ecx
  int v11; // r9d
  unsigned __int64 v12; // rcx
  void *v13; // rax
  __int64 v14; // rax
  void *v15; // rax
  UINT puResult; // [rsp+40h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 41);
  v4 = *((_DWORD *)this + 43);
  *a2 = 0;
  if ( v2 == 16 )
  {
    v6 = 15;
    goto LABEL_35;
  }
  if ( v2 != 22 && v2 != 23 )
  {
    if ( v2 != 69 )
    {
      if ( v2 - 72 >= 2 )
      {
        v6 = v2;
        goto LABEL_7;
      }
      goto LABEL_21;
    }
    v6 = 68;
LABEL_35:
    *a2 = 1;
    goto LABEL_7;
  }
LABEL_21:
  *a2 = 1;
  v6 = 71;
  if ( (unsigned int)HasAlphaChannel(v4) || (unsigned int)(v11 - 22) <= 1 )
  {
    v12 = 6LL * *((unsigned int *)this + 52);
    if ( v12 > 0xFFFFFFFF )
    {
      v8 = -2147024362;
LABEL_26:
      if ( !g_doStackCaptures )
        return v8;
      v10 = v8;
      goto LABEL_20;
    }
    v13 = malloc((unsigned int)v12);
    *((_QWORD *)this + 27) = v13;
    if ( !v13 )
    {
LABEL_25:
      v8 = -2147024882;
      goto LABEL_26;
    }
  }
LABEL_7:
  switch ( *((_DWORD *)this + 43) )
  {
    case 0x10:
      v4 = 15;
LABEL_16:
      *a2 = 1;
      goto LABEL_12;
    case 0x16:
    case 0x17:
LABEL_28:
      v14 = *((unsigned int *)this + 52);
      *a2 = 1;
      puResult = 0;
      v7 = ULongLongToUInt(6 * v14, &puResult);
      v8 = v7;
      if ( v7 < 0 )
      {
LABEL_13:
        if ( !g_doStackCaptures )
          return v8;
        v10 = v7;
LABEL_20:
        DoStackCapture(v10);
        return v8;
      }
      v15 = malloc(puResult);
      *((_QWORD *)this + 28) = v15;
      if ( v15 )
      {
        v4 = 71;
        goto LABEL_12;
      }
      goto LABEL_25;
    case 0x45:
      v4 = 68;
      goto LABEL_16;
  }
  if ( (unsigned int)(*((_DWORD *)this + 43) - 72) < 2 )
    goto LABEL_28;
LABEL_12:
  v7 = CIcmColorTransform::TranslatePixelFormat(v6, (char *)this + 160);
  v8 = v7;
  if ( v7 < 0 )
    goto LABEL_13;
  v7 = CIcmColorTransform::TranslatePixelFormat(v4, (char *)this + 168);
  v8 = v7;
  if ( v7 < 0 )
    goto LABEL_13;
  return v8;
}

```

## disassembly

```asm
0x180009fb4  mov     [rsp+arg_8], rbx
0x180009fb9  mov     [rsp+arg_10], rbp
0x180009fbe  push    rsi
0x180009fbf  push    rdi
0x180009fc0  push    r15
0x180009fc2  sub     rsp, 20h
0x180009fc6  mov     r9d, [rcx+0A4h]
0x180009fcd  mov     rbx, rdx
0x180009fd0  mov     esi, [rcx+0ACh]
0x180009fd6  mov     r8d, r9d
0x180009fd9  mov     dword ptr [rdx], 0
0x180009fdf  mov     rdi, rcx
0x180009fe2  mov     r15d, 1
0x180009fe8  sub     r8d, 10h
0x180009fec  jz      loc_18000A180
0x180009ff2  sub     r8d, 6
0x180009ff6  jz      loc_18000A0B8
0x180009ffc  sub     r8d, r15d
0x180009fff  jz      loc_18000A0B8
0x18000a005  sub     r8d, 2Eh ; '.'
0x18000a009  jz      loc_18000A167
0x18000a00f  sub     r8d, 3
0x18000a013  jz      loc_18000A0B8
0x18000a019  cmp     r8d, r15d
0x18000a01c  jz      loc_18000A0B8
0x18000a022  mov     ebp, r9d
0x18000a025  mov     ecx, [rdi+0ACh]
0x18000a02b  sub     ecx, 10h
0x18000a02e  jz      short loc_18000A08F
0x18000a030  sub     ecx, 6
0x18000a033  jz      loc_18000A11B
0x18000a039  sub     ecx, r15d
0x18000a03c  jz      loc_18000A11B
0x18000a042  sub     ecx, 2Eh ; '.'
0x18000a045  jz      loc_18000A18D
0x18000a04b  sub     ecx, 3
0x18000a04e  jz      loc_18000A11B
0x18000a054  cmp     ecx, r15d
0x18000a057  jz      loc_18000A11B
0x18000a05d  lea     rdx, [rdi+0A0h]
0x18000a064  mov     ecx, ebp
0x18000a066  call    ?TranslatePixelFormat@CIcmColorTransform@@KAJW4Enum@MilPixelFormat@@AEAW4BMFORMAT@@@Z; CIcmColorTransform::TranslatePixelFormat(MilPixelFormat::Enum,BMFORMAT &)
0x18000a06b  mov     ebx, eax
0x18000a06d  test    eax, eax
0x18000a06f  jns     short loc_18000A099
0x18000a071  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000a078  jnz     short loc_18000A0AF
0x18000a07a  mov     rbp, [rsp+38h+arg_10]
0x18000a07f  mov     eax, ebx
0x18000a081  mov     rbx, [rsp+38h+arg_8]
0x18000a086  add     rsp, 20h
0x18000a08a  pop     r15
0x18000a08c  pop     rdi
0x18000a08d  pop     rsi
0x18000a08e  retn
0x18000a08f  mov     esi, 0Fh
0x18000a094  mov     [rbx], r15d
0x18000a097  jmp     short loc_18000A05D
0x18000a099  lea     rdx, [rdi+0A8h]
0x18000a0a0  mov     ecx, esi
0x18000a0a2  call    ?TranslatePixelFormat@CIcmColorTransform@@KAJW4Enum@MilPixelFormat@@AEAW4BMFORMAT@@@Z; CIcmColorTransform::TranslatePixelFormat(MilPixelFormat::Enum,BMFORMAT &)
0x18000a0a7  mov     ebx, eax
0x18000a0a9  test    eax, eax
0x18000a0ab  js      short loc_18000A071
0x18000a0ad  jmp     short loc_18000A07A
0x18000a0af  mov     ecx, eax; int
0x18000a0b1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000a0b6  jmp     short loc_18000A07A
0x18000a0b8  mov     ecx, esi
0x18000a0ba  mov     [rdx], r15d
0x18000a0bd  mov     ebp, 47h ; 'G'
0x18000a0c2  call    ?HasAlphaChannel@@YAHW4Enum@MilPixelFormat@@H@Z; HasAlphaChannel(MilPixelFormat::Enum,int)
0x18000a0c7  test    eax, eax
0x18000a0c9  jz      loc_18000A16E
0x18000a0cf  mov     eax, [rdi+0D0h]
0x18000a0d5  lea     rcx, [rax+rax*2]
0x18000a0d9  mov     eax, 0FFFFFFFFh
0x18000a0de  add     rcx, rcx
0x18000a0e1  cmp     rcx, rax
0x18000a0e4  jbe     short loc_18000A0ED
0x18000a0e6  mov     ebx, 80070216h
0x18000a0eb  jmp     short loc_18000A10A
0x18000a0ed  mov     ecx, ecx; Size
0x18000a0ef  call    cs:__imp_malloc
0x18000a0f5  mov     [rdi+0D8h], rax
0x18000a0fc  test    rax, rax
0x18000a0ff  jnz     loc_18000A025
0x18000a105  mov     ebx, 8007000Eh
0x18000a10a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000a111  jz      loc_18000A07A
0x18000a117  mov     ecx, ebx
0x18000a119  jmp     short loc_18000A0B1
0x18000a11b  mov     eax, [rdi+0D0h]
0x18000a121  lea     rdx, [rsp+38h+puResult]; puResult
0x18000a126  mov     [rbx], r15d
0x18000a129  mov     [rsp+38h+puResult], 0
0x18000a131  lea     rcx, [rax+rax*2]
0x18000a135  add     rcx, rcx; ullOperand
0x18000a138  call    ULongLongToUInt
0x18000a13d  mov     ebx, eax
0x18000a13f  test    eax, eax
0x18000a141  js      loc_18000A071
0x18000a147  mov     ecx, [rsp+38h+puResult]; Size
0x18000a14b  call    cs:__imp_malloc
0x18000a151  mov     [rdi+0E0h], rax
0x18000a158  test    rax, rax
0x18000a15b  jz      short loc_18000A105
0x18000a15d  mov     esi, 47h ; 'G'
0x18000a162  jmp     loc_18000A05D
0x18000a167  mov     ebp, 44h ; 'D'
0x18000a16c  jmp     short loc_18000A185
0x18000a16e  lea     eax, [r9-16h]
0x18000a172  cmp     eax, r15d
0x18000a175  ja      loc_18000A025
0x18000a17b  jmp     loc_18000A0CF
0x18000a180  mov     ebp, 0Fh
0x18000a185  mov     [rdx], r15d
0x18000a188  jmp     loc_18000A025
0x18000a18d  mov     esi, 44h ; 'D'
0x18000a192  jmp     loc_18000A094
```
