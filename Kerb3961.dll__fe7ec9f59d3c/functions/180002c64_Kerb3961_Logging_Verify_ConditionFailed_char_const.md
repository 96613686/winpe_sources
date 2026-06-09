# Kerb3961::Logging::Verify::ConditionFailed(char const *)

- ea: `0x180002c64`
- end: `0x180002d0f`
- name: `?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z`
- size: `171`
- prototype: `void __fastcall(Kerb3961::Logging::Verify *__hidden this, const char *)`
- caller_count: `105`
- callee_count: `3`
- tags: ``

## callers

- `0x180004118`
- `0x180004940`
- `0x180004b40`
- `0x180004cf4`
- `0x180004e74`
- `0x180004fac`
- `0x180005480`
- `0x180005ed0`
- `0x180006270`
- `0x180006ee0`
- `0x18000700c`
- `0x18000712c`
- `0x1800071e0`
- `0x180007500`
- `0x180007650`
- `0x1800079d0`
- `0x180007a90`
- `0x180007c80`
- `0x180007d00`
- `0x180007fb0`
- `0x1800082f0`
- `0x180008500`
- `0x1800085cc`
- `0x180008a5c`
- `0x18000901c`
- `0x180009190`
- `0x1800092a4`
- `0x1800093a0`
- `0x180009470`
- `0x1800095b0`
- `0x1800098c0`
- `0x180009c50`
- `0x180009dc0`
- `0x18000a090`
- `0x18000a2a0`
- `0x18000a794`
- `0x18000aa04`
- `0x18000ab94`
- `0x18000ae18`
- `0x18000b0f0`
- `0x18000b210`
- `0x18000b300`
- `0x18000b3d0`
- `0x18000b840`
- `0x18000ba20`
- `0x18000bcd0`
- `0x18000c060`
- `0x18000c1c0`
- `0x18000c350`
- `0x18000c4c8`

## callees

- `0x18000120c`
- `0x180001d40`
- `0x180002c64`

## pseudocode

```c
void __fastcall Kerb3961::Logging::Verify::ConditionFailed(Kerb3961::Logging::Verify *this, const char *a2)
{
  int v2; // edx
  __int64 v3; // rdx
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-48h] BYREF
  Kerb3961::Logging::Verify *v5; // [rsp+50h] [rbp-28h]
  int v6; // [rsp+58h] [rbp-20h]
  int v7; // [rsp+5Ch] [rbp-1Ch]

  if ( (unsigned int)dword_180029000 > 2 )
  {
    v2 = 1;
    if ( (qword_180029010 & 1) != 0 && (qword_180029018 & 1) == qword_180029018 )
    {
      if ( this )
      {
        v3 = -1;
        do
          ++v3;
        while ( *((_BYTE *)this + v3) );
        v2 = v3 + 1;
      }
      else
      {
        this = (Kerb3961::Logging::Verify *)&word_1800205DA;
      }
      v5 = this;
      v6 = v2;
      v7 = 0;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180029000, (unsigned __int8 *)byte_180025F71, 0, 0, 3u, &v4);
    }
  }
}

```

## disassembly

```asm
0x180002c64  sub     rsp, 78h
0x180002c68  mov     rax, cs:__security_cookie
0x180002c6f  xor     rax, rsp
0x180002c72  mov     [rsp+78h+var_18], rax
0x180002c77  mov     eax, cs:dword_180029000
0x180002c7d  cmp     eax, 2
0x180002c80  jbe     short loc_180002CFD
0x180002c82  mov     r8, cs:qword_180029018
0x180002c89  mov     edx, 1
0x180002c8e  mov     rax, cs:qword_180029010
0x180002c95  test    dl, al
0x180002c97  jz      short loc_180002CFD
0x180002c99  mov     rax, r8
0x180002c9c  and     rax, rdx
0x180002c9f  cmp     rax, r8
0x180002ca2  jnz     short loc_180002CFD
0x180002ca4  test    rcx, rcx
0x180002ca7  jz      short loc_180002CBA
0x180002ca9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180002cad  inc     rdx
0x180002cb0  cmp     byte ptr [rcx+rdx], 0
0x180002cb4  jnz     short loc_180002CAD
0x180002cb6  inc     edx
0x180002cb8  jmp     short loc_180002CC1
0x180002cba  lea     rcx, word_1800205DA
0x180002cc1  lea     rax, [rsp+78h+var_48]
0x180002cc6  mov     [rsp+78h+var_28], rcx
0x180002ccb  mov     [rsp+78h+var_20], edx
0x180002ccf  lea     rcx, dword_180029000
0x180002cd6  mov     [rsp+78h+var_50], rax
0x180002cdb  lea     rdx, byte_180025F71
0x180002ce2  xor     r9d, r9d
0x180002ce5  mov     [rsp+78h+var_58], 3
0x180002ced  xor     r8d, r8d
0x180002cf0  mov     [rsp+78h+var_1C], 0
0x180002cf8  call    _tlgWriteTransfer_EventWriteTransfer
0x180002cfd  mov     rcx, [rsp+78h+var_18]
0x180002d02  xor     rcx, rsp; StackCookie
0x180002d05  call    __security_check_cookie
0x180002d0a  add     rsp, 78h
0x180002d0e  retn
```
