# APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)

- ea: `0x18002bd3c`
- end: `0x18002be1f`
- name: `?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z`
- size: `227`
- prototype: `__int64 __fastcall(APP_OBJECT_UTILS *__hidden this, struct IExtensionContext *, struct ICommandParameterList *)`
- caller_count: `25`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010cc0`
- `0x180011690`
- `0x180014010`
- `0x180014690`
- `0x180015ab0`
- `0x180016200`
- `0x180017560`
- `0x180017a24`
- `0x180017f90`
- `0x180018fd0`
- `0x18001a850`
- `0x18001b7e4`
- `0x18001ca1c`
- `0x18001e590`
- `0x18001f120`
- `0x1800200b0`
- `0x180021658`
- `0x180022a9c`
- `0x180023740`
- `0x180023ba8`
- `0x180025170`
- `0x180025748`
- `0x180025fe4`
- `0x180027190`
- `0x180028f50`

## callees

- `0x18002bd3c`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall APP_OBJECT_UTILS::ValidateEmptyParameters(
        APP_OBJECT_UTILS *this,
        struct IExtensionContext *a2,
        struct ICommandParameterList *a3)
{
  int v5; // ebx
  _QWORD v7[5]; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+60h] [rbp+8h] BYREF
  int v9; // [rsp+64h] [rbp+Ch]
  __int64 v10; // [rsp+70h] [rbp+18h] BYREF
  __int64 v11; // [rsp+78h] [rbp+20h] BYREF

  v9 = HIDWORD(this);
  v7[0] = 0;
  v10 = 0;
  v8 = 0;
  v11 = 0;
  if ( a3 && a2 )
  {
    v5 = 0;
    if ( ((*(__int64 (__fastcall **)(struct IExtensionContext *))(*(_QWORD *)a2 + 32LL))(a2) & 2) == 0 )
    {
      v5 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, int *))(*(_QWORD *)a3 + 24LL))(a3, &v8);
      if ( v5 >= 0 )
      {
        if ( v8 )
        {
          v5 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, _QWORD, __int64 *, _QWORD *))(*(_QWORD *)a3 + 32LL))(
                 a3,
                 0,
                 &v10,
                 v7);
          if ( v5 >= 0 )
          {
            v11 = v10;
            v5 = -2147024809;
            (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, __int64 *, _DWORD))(*(_QWORD *)a2 + 144LL))(
              a2,
              2147942487LL,
              3221226528LL,
              &v11,
              0);
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002bd3c  mov     rax, rsp
0x18002bd3f  mov     [rax+8], rcx
0x18002bd43  push    rbx
0x18002bd44  push    rsi
0x18002bd45  push    rdi
0x18002bd46  sub     rsp, 40h
0x18002bd4a  mov     qword ptr [rax-28h], 0
0x18002bd52  mov     rsi, r8
0x18002bd55  mov     qword ptr [rax+18h], 0
0x18002bd5d  mov     rdi, rdx
0x18002bd60  mov     dword ptr [rax+8], 0
0x18002bd67  mov     qword ptr [rax+20h], 0
0x18002bd6f  test    r8, r8
0x18002bd72  jz      loc_18002BE10
0x18002bd78  test    rdx, rdx
0x18002bd7b  jz      loc_18002BE10
0x18002bd81  mov     rax, [rdx]
0x18002bd84  mov     rcx, rdx
0x18002bd87  xor     ebx, ebx
0x18002bd89  mov     rax, [rax+20h]
0x18002bd8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd92  test    al, 2
0x18002bd94  jnz     short loc_18002BE15
0x18002bd96  mov     rax, [rsi]
0x18002bd99  lea     rdx, [rsp+58h+arg_0]
0x18002bd9e  mov     rcx, rsi
0x18002bda1  mov     rax, [rax+18h]
0x18002bda5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdaa  mov     ebx, eax
0x18002bdac  test    eax, eax
0x18002bdae  js      short loc_18002BE15
0x18002bdb0  cmp     [rsp+58h+arg_0], 0
0x18002bdb5  jbe     short loc_18002BE15
0x18002bdb7  mov     rax, [rsi]
0x18002bdba  lea     r9, [rsp+58h+var_28]
0x18002bdbf  lea     r8, [rsp+58h+arg_10]
0x18002bdc4  xor     edx, edx
0x18002bdc6  mov     rcx, rsi
0x18002bdc9  mov     rax, [rax+20h]
0x18002bdcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdd2  mov     ebx, eax
0x18002bdd4  test    eax, eax
0x18002bdd6  js      short loc_18002BE15
0x18002bdd8  mov     rax, [rsp+58h+arg_10]
0x18002bddd  lea     r9, [rsp+58h+arg_18]
0x18002bde2  mov     [rsp+58h+arg_18], rax
0x18002bde7  mov     ebx, 80070057h
0x18002bdec  mov     rax, [rdi]
0x18002bdef  mov     r8d, 0C0000420h
0x18002bdf5  mov     edx, ebx
0x18002bdf7  mov     [rsp+58h+var_38], 0
0x18002bdff  mov     rcx, rdi
0x18002be02  mov     rax, [rax+90h]
0x18002be09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be0e  jmp     short loc_18002BE15
0x18002be10  mov     ebx, 80070057h
0x18002be15  mov     eax, ebx
0x18002be17  add     rsp, 40h
0x18002be1b  pop     rdi
0x18002be1c  pop     rsi
0x18002be1d  pop     rbx
0x18002be1e  retn
```
