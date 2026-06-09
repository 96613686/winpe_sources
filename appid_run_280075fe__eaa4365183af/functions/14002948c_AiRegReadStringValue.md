# AiRegReadStringValue

- ea: `0x14002948c`
- end: `0x1400295e2`
- name: `AiRegReadStringValue`
- size: `342`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140028040`
- `0x140028f80`
- `0x14002d1bc`
- `0x14002d868`

## callees

- `0x140006c40`
- `0x14002948c`
- `0x1400328b0`
- `0x140032a50`
- `0x1400331a0`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x140029509`
- `ntoskrnl!ZwQueryValueKey` at `0x140029509`
- `ntoskrnl!ZwClose` at `0x1400295c6`
- `ntoskrnl!ZwClose` at `0x1400295c6`

## pseudocode

```c
__int64 __fastcall AiRegReadStringValue(void *a1, struct _UNICODE_STRING *a2, struct _UNICODE_STRING *a3, __int64 a4)
{
  _DWORD *v6; // rdi
  NTSTATUS v7; // ebx
  ULONG Length; // ebx
  NTSTATUS v9; // eax
  int v10; // r8d
  unsigned int v11; // edx
  unsigned int v12; // edx
  __int64 v13; // rcx
  void *v14; // rax
  ULONG ResultLength; // [rsp+30h] [rbp-48h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-40h] BYREF

  ResultLength = 48;
  KeyHandle = 0;
  v6 = 0;
  v7 = AiRegOpenKey(a1, a2, 0x20019u, &KeyHandle);
  if ( v7 >= 0 )
  {
    while ( 1 )
    {
      Length = ResultLength;
      AiFree(v6);
      v6 = (_DWORD *)AiAlloc(Length);
      if ( !v6 )
        break;
      v9 = ZwQueryValueKey(KeyHandle, a3, KeyValuePartialInformation, v6, Length, &ResultLength);
      v7 = v9;
      if ( v9 != -2147483643 )
      {
        if ( v9 < 0 )
          goto LABEL_18;
        v10 = v6[1];
        if ( v10 != 1 && v10 != 7 || (v11 = v6[2], v11 - 2 > 0xFFFD) || (v11 & 1) != 0 )
        {
          v7 = -1073741788;
          goto LABEL_18;
        }
        v12 = v11 >> 1;
        if ( *((_WORD *)v6 + v12 + 5) || v10 == 7 && v12 != 1 && *((_WORD *)v6 + v12 + 4) )
        {
          v7 = -1073739509;
          goto LABEL_18;
        }
        *(_WORD *)a4 = *((_WORD *)v6 + 4) - 2;
        v13 = *((unsigned __int16 *)v6 + 4);
        *(_WORD *)(a4 + 2) = *((_WORD *)v6 + 4);
        v14 = (void *)AiAlloc(v13);
        *(_QWORD *)(a4 + 8) = v14;
        if ( v14 )
        {
          memmove(v14, v6 + 3, *(unsigned __int16 *)(a4 + 2));
          goto LABEL_18;
        }
        break;
      }
    }
    v7 = -1073741801;
  }
LABEL_18:
  AiFree(v6);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14002948c  push    rbx
0x14002948e  push    rbp
0x14002948f  push    rsi
0x140029490  push    rdi
0x140029491  push    r14
0x140029493  push    r15
0x140029495  sub     rsp, 48h
0x140029499  mov     r14, r9
0x14002949c  mov     [rsp+78h+var_48], 30h ; '0'
0x1400294a4  mov     rsi, r8
0x1400294a7  lea     r9, [rsp+78h+KeyHandle]
0x1400294ac  xor     ebp, ebp
0x1400294ae  mov     r8d, 20019h
0x1400294b4  mov     [rsp+78h+KeyHandle], rbp
0x1400294b9  mov     edi, ebp
0x1400294bb  call    AiRegOpenKey
0x1400294c0  mov     ebx, eax
0x1400294c2  test    eax, eax
0x1400294c4  js      loc_1400295B4
0x1400294ca  lea     r15d, [rbp+2]
0x1400294ce  mov     ebx, [rsp+78h+var_48]
0x1400294d2  mov     rcx, rdi
0x1400294d5  call    AiFree
0x1400294da  mov     ecx, ebx
0x1400294dc  call    AiAlloc
0x1400294e1  mov     rdi, rax
0x1400294e4  test    rax, rax
0x1400294e7  jz      loc_1400295AF
0x1400294ed  mov     rcx, [rsp+78h+KeyHandle]; KeyHandle
0x1400294f2  lea     rax, [rsp+78h+var_48]
0x1400294f7  mov     [rsp+78h+ResultLength], rax; ResultLength
0x1400294fc  mov     r9, rdi; KeyValueInformation
0x1400294ff  mov     r8d, r15d; KeyValueInformationClass
0x140029502  mov     [rsp+78h+Length], ebx; Length
0x140029506  mov     rdx, rsi; ValueName
0x140029509  call    cs:__imp_ZwQueryValueKey
0x140029510  nop     dword ptr [rax+rax+00h]
0x140029515  mov     ebx, eax
0x140029517  cmp     eax, 80000005h
0x14002951c  jz      short loc_1400294CE
0x14002951e  test    eax, eax
0x140029520  js      loc_1400295B4
0x140029526  mov     r8d, [rdi+4]
0x14002952a  cmp     r8d, 1
0x14002952e  jz      short loc_14002953D
0x140029530  cmp     r8d, 7
0x140029534  jz      short loc_14002953D
0x140029536  mov     ebx, 0C0000024h
0x14002953b  jmp     short loc_1400295B4
0x14002953d  mov     edx, [rdi+8]
0x140029540  lea     eax, [rdx-2]
0x140029543  cmp     eax, 0FFFDh
0x140029548  ja      short loc_140029536
0x14002954a  test    dl, 1
0x14002954d  jnz     short loc_140029536
0x14002954f  shr     edx, 1
0x140029551  lea     eax, [rdx-1]
0x140029554  cmp     [rdi+rax*2+0Ch], bp
0x140029559  jnz     short loc_1400295A8
0x14002955b  cmp     r8d, 7
0x14002955f  jnz     short loc_140029570
0x140029561  cmp     edx, 1
0x140029564  jz      short loc_140029570
0x140029566  lea     eax, [rdx-2]
0x140029569  cmp     [rdi+rax*2+0Ch], bp
0x14002956e  jnz     short loc_1400295A8
0x140029570  movzx   eax, word ptr [rdi+8]
0x140029574  sub     ax, r15w
0x140029578  mov     [r14], ax
0x14002957c  movzx   eax, word ptr [rdi+8]
0x140029580  mov     ecx, eax
0x140029582  mov     [r14+2], ax
0x140029587  call    AiAlloc
0x14002958c  mov     [r14+8], rax
0x140029590  test    rax, rax
0x140029593  jz      short loc_1400295AF
0x140029595  movzx   r8d, word ptr [r14+2]; Size
0x14002959a  lea     rdx, [rdi+0Ch]; Src
0x14002959e  mov     rcx, rax; void *
0x1400295a1  call    memmove
0x1400295a6  jmp     short loc_1400295B4
0x1400295a8  mov     ebx, 0C000090Bh
0x1400295ad  jmp     short loc_1400295B4
0x1400295af  mov     ebx, 0C0000017h
0x1400295b4  mov     rcx, rdi
0x1400295b7  call    AiFree
0x1400295bc  mov     rcx, [rsp+78h+KeyHandle]; Handle
0x1400295c1  test    rcx, rcx
0x1400295c4  jz      short loc_1400295D2
0x1400295c6  call    cs:__imp_ZwClose
0x1400295cd  nop     dword ptr [rax+rax+00h]
0x1400295d2  mov     eax, ebx
0x1400295d4  add     rsp, 48h
0x1400295d8  pop     r15
0x1400295da  pop     r14
0x1400295dc  pop     rdi
0x1400295dd  pop     rsi
0x1400295de  pop     rbp
0x1400295df  pop     rbx
0x1400295e0  retn
```
