# Kerb3961::Logging::Verify::ConditionFailed(char const *)

- ea: `0x180011760`
- end: `0x18001180c`
- name: `?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z`
- size: `172`
- prototype: `void __fastcall(Kerb3961::Logging::Verify *__hidden this, const char *)`
- caller_count: `87`
- callee_count: `3`
- tags: ``

## callers

- `0x180001464`
- `0x180001940`
- `0x1800019a0`
- `0x180001e7c`
- `0x180001ff4`
- `0x180002174`
- `0x1800022a8`
- `0x1800025e0`
- `0x1800028d4`
- `0x180002cc4`
- `0x180003020`
- `0x180003240`
- `0x1800037e0`
- `0x180003910`
- `0x180003a54`
- `0x180003b10`
- `0x180003dc0`
- `0x180004390`
- `0x180004700`
- `0x180004a00`
- `0x180004ec0`
- `0x180004f80`
- `0x180005160`
- `0x1800051e0`
- `0x1800054a0`
- `0x180005550`
- `0x180005950`
- `0x1800059e4`
- `0x180005b1c`
- `0x180005e34`
- `0x180005f40`
- `0x180005fb0`
- `0x1800060f0`
- `0x1800063f0`
- `0x180006750`
- `0x180006900`
- `0x180006b30`
- `0x180006cc8`
- `0x180006df0`
- `0x180006f6c`
- `0x1800070e0`
- `0x180007338`
- `0x180007710`
- `0x180007ad0`
- `0x180007e9c`
- `0x180008020`
- `0x1800083f0`
- `0x180008840`
- `0x180008aa0`
- `0x180008b40`

## callees

- `0x180001008`
- `0x180011760`
- `0x180012200`

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

  if ( (unsigned int)dword_18001A000 > 2 )
  {
    v2 = 1;
    if ( (qword_18001A010 & 1) != 0 && (qword_18001A018 & 1) == qword_18001A018 )
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
        this = (Kerb3961::Logging::Verify *)&unk_1800187AE;
      }
      v5 = this;
      v6 = v2;
      v7 = 0;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_18001A000, byte_1800188C1, 0, 0, 3u, &v4);
    }
  }
}

```

## disassembly

```asm
0x180011760  sub     rsp, 78h
0x180011764  mov     rax, cs:__security_cookie
0x18001176b  xor     rax, rsp
0x18001176e  mov     [rsp+78h+var_18], rax
0x180011773  mov     eax, cs:dword_18001A000
0x180011779  cmp     eax, 2
0x18001177c  jbe     short loc_1800117F9
0x18001177e  mov     r8, cs:qword_18001A018
0x180011785  mov     edx, 1
0x18001178a  mov     rax, cs:qword_18001A010
0x180011791  test    dl, al
0x180011793  jz      short loc_1800117F9
0x180011795  mov     rax, r8
0x180011798  and     rax, rdx
0x18001179b  cmp     rax, r8
0x18001179e  jnz     short loc_1800117F9
0x1800117a0  test    rcx, rcx
0x1800117a3  jz      short loc_1800117B6
0x1800117a5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800117a9  inc     rdx
0x1800117ac  cmp     byte ptr [rcx+rdx], 0
0x1800117b0  jnz     short loc_1800117A9
0x1800117b2  inc     edx
0x1800117b4  jmp     short loc_1800117BD
0x1800117b6  lea     rcx, unk_1800187AE
0x1800117bd  lea     rax, [rsp+78h+var_48]
0x1800117c2  mov     [rsp+78h+var_28], rcx
0x1800117c7  mov     [rsp+78h+var_20], edx
0x1800117cb  lea     rcx, dword_18001A000
0x1800117d2  mov     [rsp+78h+var_50], rax
0x1800117d7  lea     rdx, byte_1800188C1
0x1800117de  xor     r9d, r9d
0x1800117e1  mov     [rsp+78h+var_58], 3
0x1800117e9  xor     r8d, r8d
0x1800117ec  mov     [rsp+78h+var_1C], 0
0x1800117f4  call    _tlgWriteTransfer_EtwWriteTransfer
0x1800117f9  mov     rcx, [rsp+78h+var_18]
0x1800117fe  xor     rcx, rsp; StackCookie
0x180011801  call    __security_check_cookie
0x180011806  add     rsp, 78h
0x18001180a  retn
```
