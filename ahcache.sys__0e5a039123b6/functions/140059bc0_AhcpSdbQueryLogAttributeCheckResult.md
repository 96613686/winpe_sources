# AhcpSdbQueryLogAttributeCheckResult

- ea: `0x140059bc0`
- end: `0x140059d70`
- name: `AhcpSdbQueryLogAttributeCheckResult`
- size: `432`
- prototype: `char __fastcall(unsigned __int16, __int64, unsigned int, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400079f0`
- `0x1400304c0`
- `0x140059bc0`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x140059c9c`
- `ntoskrnl!EtwEventEnabled` at `0x140059c9c`
- `ntoskrnl!EtwWrite` at `0x140059d3b`
- `ntoskrnl!EtwWrite` at `0x140059d3b`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140059c34`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140059c34`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140059c1f`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140059c1f`

## pseudocode

```c
char __fastcall AhcpSdbQueryLogAttributeCheckResult(unsigned __int16 a1, __int64 a2, unsigned int a3, int a4)
{
  unsigned int v4; // ebx
  __int64 CurrentServerSilo; // rax
  int v9; // eax
  REGHANDLE *v10; // rdi
  REGHANDLE v11; // rdi
  const EVENT_DESCRIPTOR *v12; // rbx
  __int64 v13; // r9
  ULONG v14; // r10d
  __int64 v15; // rax
  __int64 v17; // [rsp+38h] [rbp-29h] BYREF
  _BYTE UserData[24]; // [rsp+48h] [rbp-19h] BYREF
  __int128 v19; // [rsp+60h] [rbp-1h]
  __int128 v20; // [rsp+70h] [rbp+Fh]
  __int64 v21; // [rsp+80h] [rbp+1Fh]
  int v22; // [rsp+E0h] [rbp+7Fh] BYREF

  v22 = a4;
  v4 = g_AhcacheSiloContextSlot;
  memset(UserData, 0, sizeof(UserData));
  v21 = 0;
  v19 = 0;
  v17 = 0;
  v20 = 0;
  CurrentServerSilo = PsGetCurrentServerSilo();
  PsGetPermanentSiloContext(CurrentServerSilo, v4, &v17);
  LOBYTE(v9) = v17;
  v10 = *(REGHANDLE **)(v17 + 104);
  if ( v10 )
  {
    v11 = *v10;
    if ( v11 )
    {
      v9 = a1 & 0xF000;
      switch ( v9 )
      {
        case 16384:
          v12 = (const EVENT_DESCRIPTOR *)SdbApiMatchMessageDWord;
          break;
        case 20480:
          v12 = (const EVENT_DESCRIPTOR *)SdbApiMatchMessageQWord;
          break;
        case 24576:
          v12 = &SdbApiMatchMessageStringW;
          break;
        default:
          return v9;
      }
      LOBYTE(v9) = EtwEventEnabled(v11, v12);
      if ( (_BYTE)v9 )
      {
        *(_QWORD *)&v19 = 28;
        *(_QWORD *)UserData = &v22;
        *(_QWORD *)&UserData[8] = 4;
        *(_QWORD *)&UserData[16] = L"FileAttribute";
        *((_QWORD *)&v20 + 1) = a2;
        v21 = a3;
        v13 = SdbTagToString(a1);
        if ( v13 )
        {
          v15 = -1;
          do
            ++v15;
          while ( *(_WORD *)(v13 + 2 * v15) );
          *((_QWORD *)&v19 + 1) = v13;
          *(_QWORD *)&v20 = (unsigned int)(2 * v15 + 2);
        }
        else
        {
          *(_QWORD *)&v20 = 16;
          *((_QWORD *)&v19 + 1) = L"Unknown";
        }
        LOBYTE(v9) = EtwWrite(v11, v12, 0, v14, (PEVENT_DATA_DESCRIPTOR)UserData);
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x140059bc0  mov     rax, rsp
0x140059bc3  mov     [rax+10h], rbx
0x140059bc7  mov     [rax+18h], rsi
0x140059bcb  mov     [rax+20h], r9d
0x140059bcf  push    rbp
0x140059bd0  push    rdi
0x140059bd1  push    r12
0x140059bd3  push    r14
0x140059bd5  push    r15
0x140059bd7  lea     rbp, [rax-5Fh]
0x140059bdb  sub     rsp, 90h
0x140059be2  mov     rax, cs:__security_cookie
0x140059be9  xor     rax, rsp
0x140059bec  mov     [rbp+57h+var_30], rax
0x140059bf0  mov     ebx, cs:g_AhcacheSiloContextSlot
0x140059bf6  xorps   xmm0, xmm0
0x140059bf9  xor     r12d, r12d
0x140059bfc  movzx   esi, cx
0x140059bff  xor     eax, eax
0x140059c01  mov     qword ptr [rbp+57h+var_70], r12
0x140059c05  movups  xmmword ptr [rbp+57h+var_70+8], xmm0
0x140059c09  mov     [rbp+57h+var_38], rax
0x140059c0d  mov     r14d, r8d
0x140059c10  movups  [rbp+57h+var_58], xmm0
0x140059c14  mov     [rbp+57h+var_80], r12
0x140059c18  mov     r15, rdx
0x140059c1b  movups  [rbp+57h+var_48], xmm0
0x140059c1f  call    cs:__imp_PsGetCurrentServerSilo
0x140059c26  nop     dword ptr [rax+rax+00h]
0x140059c2b  lea     r8, [rbp+57h+var_80]
0x140059c2f  mov     edx, ebx
0x140059c31  mov     rcx, rax
0x140059c34  call    cs:__imp_PsGetPermanentSiloContext
0x140059c3b  nop     dword ptr [rax+rax+00h]
0x140059c40  mov     rax, [rbp+57h+var_80]
0x140059c44  mov     rdi, [rax+68h]
0x140059c48  test    rdi, rdi
0x140059c4b  jz      loc_140059D47
0x140059c51  mov     rdi, [rdi]
0x140059c54  test    rdi, rdi
0x140059c57  jz      loc_140059D47
0x140059c5d  mov     eax, esi
0x140059c5f  and     eax, 0F000h
0x140059c64  cmp     eax, 4000h
0x140059c69  jz      short loc_140059C8F
0x140059c6b  cmp     eax, 5000h
0x140059c70  jz      short loc_140059C86
0x140059c72  cmp     eax, 6000h
0x140059c77  jnz     loc_140059D47
0x140059c7d  lea     rbx, SdbApiMatchMessageStringW
0x140059c84  jmp     short loc_140059C96
0x140059c86  lea     rbx, SdbApiMatchMessageQWord
0x140059c8d  jmp     short loc_140059C96
0x140059c8f  lea     rbx, SdbApiMatchMessageDWord
0x140059c96  mov     rdx, rbx; EventDescriptor
0x140059c99  mov     rcx, rdi; RegHandle
0x140059c9c  call    cs:__imp_EtwEventEnabled
0x140059ca3  nop     dword ptr [rax+rax+00h]
0x140059ca8  test    al, al
0x140059caa  jz      loc_140059D47
0x140059cb0  lea     rax, [rbp+57h+arg_18]
0x140059cb4  mov     qword ptr [rbp+57h+var_58], 1Ch
0x140059cbc  mov     qword ptr [rbp+57h+var_70], rax
0x140059cc0  mov     r10d, 4
0x140059cc6  lea     rax, aFileattribute; "FileAttribute"
0x140059ccd  mov     qword ptr [rbp+57h+var_70+8], r10
0x140059cd1  movzx   ecx, si
0x140059cd4  mov     qword ptr [rbp+57h+var_70+10h], rax
0x140059cd8  mov     qword ptr [rbp+57h+var_48+8], r15
0x140059cdc  mov     dword ptr [rbp+57h+var_38], r14d
0x140059ce0  mov     dword ptr [rbp+57h+var_38+4], r12d
0x140059ce4  call    SdbTagToString
0x140059ce9  mov     r9, rax
0x140059cec  test    rax, rax
0x140059cef  jnz     short loc_140059D06
0x140059cf1  lea     rax, aUnknown; "Unknown"
0x140059cf8  mov     qword ptr [rbp+57h+var_48], 10h
0x140059d00  mov     qword ptr [rbp+57h+var_58+8], rax
0x140059d04  jmp     short loc_140059D26
0x140059d06  or      rax, 0FFFFFFFFFFFFFFFFh
0x140059d0a  inc     rax
0x140059d0d  cmp     [r9+rax*2], r12w
0x140059d12  jnz     short loc_140059D0A
0x140059d14  lea     eax, ds:2[rax*2]
0x140059d1b  mov     qword ptr [rbp+57h+var_58+8], r9
0x140059d1f  mov     dword ptr [rbp+57h+var_48], eax
0x140059d22  mov     dword ptr [rbp+57h+var_48+4], r12d
0x140059d26  lea     rax, [rbp+57h+var_70]
0x140059d2a  mov     r9d, r10d; UserDataCount
0x140059d2d  xor     r8d, r8d; ActivityId
0x140059d30  mov     [rsp+0B0h+UserData], rax; UserData
0x140059d35  mov     rdx, rbx; EventDescriptor
0x140059d38  mov     rcx, rdi; RegHandle
0x140059d3b  call    cs:__imp_EtwWrite
0x140059d42  nop     dword ptr [rax+rax+00h]
0x140059d47  mov     rcx, [rbp+57h+var_30]
0x140059d4b  xor     rcx, rsp; StackCookie
0x140059d4e  call    __security_check_cookie
0x140059d53  lea     r11, [rsp+0B0h+var_20]
0x140059d5b  mov     rbx, [r11+38h]
0x140059d5f  mov     rsi, [r11+40h]
0x140059d63  mov     rsp, r11
0x140059d66  pop     r15
0x140059d68  pop     r14
0x140059d6a  pop     r12
0x140059d6c  pop     rdi
0x140059d6d  pop     rbp
0x140059d6e  retn
```
