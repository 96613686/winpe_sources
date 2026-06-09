# Apx::ApfDevice::BuildCompatibleIDs(void)

- ea: `0x18000eae4`
- end: `0x18000ec98`
- name: `?BuildCompatibleIDs@ApfDevice@Apx@@AEAAJXZ`
- size: `436`
- prototype: `__int64 __fastcall(Apx::ApfDevice *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000fb6c`

## callees

- `0x18000213c`
- `0x1800027c8`
- `0x1800082b8`
- `0x18000a12c`
- `0x18000e9f4`
- `0x18000eae4`

## pseudocode

```c
__int64 __fastcall Apx::ApfDevice::BuildCompatibleIDs(Apx::ApfDevice *this)
{
  unsigned __int16 *v2; // rax
  unsigned __int16 *v3; // rbx
  int v4; // ebx
  __int64 v5; // r9
  Apx::ApfDevice *v6; // rcx
  Apx::ApfDevice *v7; // rcx
  Apx::ApfDevice *v8; // rcx
  Apx::ApfDevice *v9; // rcx
  int v11; // [rsp+20h] [rbp-10h]
  __int64 v12; // [rsp+20h] [rbp-10h]
  int v13; // [rsp+28h] [rbp-8h]
  unsigned int v14; // [rsp+48h] [rbp+18h] BYREF
  unsigned __int16 *v15; // [rsp+50h] [rbp+20h] BYREF

  v14 = 512;
  v2 = (unsigned __int16 *)operator new[](0x400u, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v2;
  v3 = v2;
  if ( v2 )
  {
    memset_0(v2, 0, 0x400u);
    v5 = *((unsigned __int16 *)this + 84);
    v13 = *((unsigned __int16 *)this + 88);
    v11 = *((unsigned __int16 *)this + 85);
    *((_QWORD *)this + 25) = v3;
    v4 = StringCchPrintfW(v3, 0x200u, L"APXENUM\\VEN_%04X&DEV_%04X&REV_%04X", v5, v11, v13);
    if ( v4 >= 0 )
    {
      v4 = Apx::ApfDevice::AdvanceToNextString(v6, &v15, &v14);
      if ( v4 >= 0 )
      {
        LODWORD(v12) = *((unsigned __int16 *)this + 85);
        v4 = StringCchPrintfW(v15, v14, L"APXENUM\\VEN_%04X&DEV_%04X", *((unsigned __int16 *)this + 84), v12);
        if ( v4 >= 0 )
        {
          v4 = Apx::ApfDevice::AdvanceToNextString(v7, &v15, &v14);
          if ( v4 >= 0 )
          {
            v4 = StringCchPrintfW(v15, v14, L"APXENUM\\VEN_%04X", *((unsigned __int16 *)this + 84));
            if ( v4 >= 0 )
            {
              v4 = Apx::ApfDevice::AdvanceToNextString(v8, &v15, &v14);
              if ( v4 >= 0 )
              {
                v4 = StringCchPrintfW(v15, v14, L"APXENUM\\APXUNIT");
                if ( v4 >= 0 )
                {
                  v4 = Apx::ApfDevice::AdvanceToNextString(v9, &v15, &v14);
                  if ( v4 >= 0 )
                  {
                    v4 = StringCchPrintfW(v15, v14, &qword_18002C8D0);
                    if ( v4 >= 0 )
                      v4 = 0;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v4 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000eae4  mov     [rsp-8+arg_0], rbx
0x18000eae9  mov     [rsp-8+arg_18], rdi
0x18000eaee  push    rbp
0x18000eaef  mov     rbp, rsp
0x18000eaf2  sub     rsp, 30h
0x18000eaf6  mov     rdi, rcx
0x18000eaf9  mov     [rbp+arg_8], 200h
0x18000eb00  mov     ecx, 400h; unsigned __int64
0x18000eb05  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000eb0c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000eb11  mov     [rbp+arg_10], rax
0x18000eb15  mov     rbx, rax
0x18000eb18  test    rax, rax
0x18000eb1b  jnz     short loc_18000EB27
0x18000eb1d  mov     ebx, 8007000Eh
0x18000eb22  jmp     loc_18000EC52
0x18000eb27  xor     edx, edx; Val
0x18000eb29  mov     r8d, 400h; Size
0x18000eb2f  mov     rcx, rbx; void *
0x18000eb32  call    memset_0
0x18000eb37  movzx   r8d, word ptr [rdi+0AAh]
0x18000eb3f  mov     edx, 200h; unsigned __int64
0x18000eb44  movzx   eax, word ptr [rdi+0B0h]
0x18000eb4b  mov     rcx, rbx; unsigned __int16 *
0x18000eb4e  movzx   r9d, word ptr [rdi+0A8h]
0x18000eb56  mov     [rsp+30h+var_8], eax
0x18000eb5a  mov     dword ptr [rsp+30h+var_10], r8d
0x18000eb5f  lea     r8, aApxenumVen04xD_1; "APXENUM\\VEN_%04X&DEV_%04X&REV_%04X"
0x18000eb66  mov     [rdi+0C8h], rbx
0x18000eb6d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000eb72  mov     ebx, eax
0x18000eb74  test    eax, eax
0x18000eb76  js      loc_18000EC52
0x18000eb7c  lea     r8, [rbp+arg_8]; unsigned int *
0x18000eb80  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x18000eb84  call    ?AdvanceToNextString@ApfDevice@Apx@@AEAAJPEAPEAGPEAK@Z; Apx::ApfDevice::AdvanceToNextString(ushort * *,ulong *)
0x18000eb89  mov     ebx, eax
0x18000eb8b  test    eax, eax
0x18000eb8d  js      loc_18000EC52
0x18000eb93  movzx   eax, word ptr [rdi+0AAh]
0x18000eb9a  lea     r8, aApxenumVen04xD_0; "APXENUM\\VEN_%04X&DEV_%04X"
0x18000eba1  movzx   r9d, word ptr [rdi+0A8h]
0x18000eba9  mov     edx, [rbp+arg_8]; unsigned __int64
0x18000ebac  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x18000ebb0  mov     dword ptr [rsp+30h+var_10], eax
0x18000ebb4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ebb9  mov     ebx, eax
0x18000ebbb  test    eax, eax
0x18000ebbd  js      loc_18000EC52
0x18000ebc3  lea     r8, [rbp+arg_8]; unsigned int *
0x18000ebc7  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x18000ebcb  call    ?AdvanceToNextString@ApfDevice@Apx@@AEAAJPEAPEAGPEAK@Z; Apx::ApfDevice::AdvanceToNextString(ushort * *,ulong *)
0x18000ebd0  mov     ebx, eax
0x18000ebd2  test    eax, eax
0x18000ebd4  js      short loc_18000EC52
0x18000ebd6  movzx   r9d, word ptr [rdi+0A8h]
0x18000ebde  lea     r8, aApxenumVen04x; "APXENUM\\VEN_%04X"
0x18000ebe5  mov     edx, [rbp+arg_8]; unsigned __int64
0x18000ebe8  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x18000ebec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ebf1  mov     ebx, eax
0x18000ebf3  test    eax, eax
0x18000ebf5  js      short loc_18000EC52
0x18000ebf7  lea     r8, [rbp+arg_8]; unsigned int *
0x18000ebfb  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x18000ebff  call    ?AdvanceToNextString@ApfDevice@Apx@@AEAAJPEAPEAGPEAK@Z; Apx::ApfDevice::AdvanceToNextString(ushort * *,ulong *)
0x18000ec04  mov     ebx, eax
0x18000ec06  test    eax, eax
0x18000ec08  js      short loc_18000EC52
0x18000ec0a  mov     edx, [rbp+arg_8]; unsigned __int64
0x18000ec0d  lea     r8, aApxenumApxunit_0; "APXENUM\\APXUNIT"
0x18000ec14  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x18000ec18  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ec1d  mov     ebx, eax
0x18000ec1f  test    eax, eax
0x18000ec21  js      short loc_18000EC52
0x18000ec23  lea     r8, [rbp+arg_8]; unsigned int *
0x18000ec27  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x18000ec2b  call    ?AdvanceToNextString@ApfDevice@Apx@@AEAAJPEAPEAGPEAK@Z; Apx::ApfDevice::AdvanceToNextString(ushort * *,ulong *)
0x18000ec30  mov     ebx, eax
0x18000ec32  test    eax, eax
0x18000ec34  js      short loc_18000EC52
0x18000ec36  mov     edx, [rbp+arg_8]; unsigned __int64
0x18000ec39  lea     r8, qword_18002C8D0; unsigned __int16 *
0x18000ec40  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x18000ec44  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ec49  mov     ebx, eax
0x18000ec4b  xor     eax, eax
0x18000ec4d  test    ebx, ebx
0x18000ec4f  cmovns  ebx, eax
0x18000ec52  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec59  lea     rax, WPP_GLOBAL_Control
0x18000ec60  cmp     rcx, rax
0x18000ec63  jz      short loc_18000EC86
0x18000ec65  test    byte ptr [rcx+1Ch], 1
0x18000ec69  jz      short loc_18000EC86
0x18000ec6b  cmp     byte ptr [rcx+19h], 5
0x18000ec6f  jb      short loc_18000EC86
0x18000ec71  mov     rcx, [rcx+10h]
0x18000ec75  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000ec7c  mov     edx, 32h ; '2'
0x18000ec81  call    WPP_SF_
0x18000ec86  mov     rdi, [rsp+30h+arg_18]
0x18000ec8b  mov     eax, ebx
0x18000ec8d  mov     rbx, [rsp+30h+arg_0]
0x18000ec92  add     rsp, 30h
0x18000ec96  pop     rbp
0x18000ec97  retn
```
