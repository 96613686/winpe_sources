# TraceLogging::IncomingCallToastActivated(uint,WindowsInternal::ApplicationModel::Calls::IncomingToastAction,long)

- ea: `0x180015944`
- end: `0x180015a74`
- name: `?IncomingCallToastActivated@TraceLogging@@SAXIW4IncomingToastAction@Calls@ApplicationModel@WindowsInternal@@J@Z`
- size: `304`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012410`

## callees

- `0x1800011fc`
- `0x180001dc0`
- `0x180011aa4`
- `0x180015944`

## pseudocode

```c
int __fastcall TraceLogging::IncomingCallToastActivated(int a1, unsigned int a2, int a3)
{
  const wchar_t *IncomingToastActionText; // rax
  const unsigned __int16 *v6; // r9
  __int64 v7; // rax
  int v8; // eax
  int v10; // [rsp+30h] [rbp-29h] BYREF
  int v11; // [rsp+34h] [rbp-25h] BYREF
  __int64 v12; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+40h] [rbp-19h] BYREF
  int *v14; // [rsp+60h] [rbp+7h]
  __int64 v15; // [rsp+68h] [rbp+Fh]
  const unsigned __int16 *v16; // [rsp+70h] [rbp+17h]
  int v17; // [rsp+78h] [rbp+1Fh]
  int v18; // [rsp+7Ch] [rbp+23h]
  int *v19; // [rsp+80h] [rbp+27h]
  __int64 v20; // [rsp+88h] [rbp+2Fh]
  __int64 *v21; // [rsp+90h] [rbp+37h]
  __int64 v22; // [rsp+98h] [rbp+3Fh]

  IncomingToastActionText = WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::GetIncomingToastActionText(a2);
  v6 = IncomingToastActionText;
  if ( (unsigned int)dword_180025000 > 5 )
  {
    LODWORD(IncomingToastActionText) = qword_180025018;
    if ( (qword_180025010 & 0x400000000000LL) != 0 && (qword_180025018 & 0x400000000000LL) == qword_180025018 )
    {
      v12 = 0x1000000;
      v21 = &v12;
      v10 = a3;
      v19 = &v10;
      v11 = a1;
      v22 = 8;
      v20 = 4;
      if ( v6 )
      {
        v7 = -1;
        do
          ++v7;
        while ( v6[v7] );
        v8 = 2 * v7 + 2;
      }
      else
      {
        v6 = &dword_18001D6C4;
        v8 = 2;
      }
      v17 = v8;
      v16 = v6;
      v14 = &v11;
      v18 = 0;
      v15 = 4;
      LODWORD(IncomingToastActionText) = tlgWriteTransfer_EventWriteTransfer(
                                           (__int64)&dword_180025000,
                                           (unsigned __int8 *)&byte_180020F93,
                                           0,
                                           0,
                                           6u,
                                           &v13);
    }
  }
  return (int)IncomingToastActionText;
}

```

## disassembly

```asm
0x180015944  mov     [rsp-8+arg_0], rbx
0x180015949  mov     [rsp-8+arg_10], rdi
0x18001594e  push    rbp
0x18001594f  lea     rbp, [rsp-57h]
0x180015954  sub     rsp, 0B0h
0x18001595b  mov     rax, cs:__security_cookie
0x180015962  xor     rax, rsp
0x180015965  mov     [rbp+57h+var_10], rax
0x180015969  mov     edi, ecx
0x18001596b  mov     ebx, r8d
0x18001596e  mov     ecx, edx
0x180015970  call    ?GetIncomingToastActionText@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@SAPEBGW4IncomingToastAction@234@@Z; WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::GetIncomingToastActionText(WindowsInternal::ApplicationModel::Calls::IncomingToastAction)
0x180015975  mov     edx, cs:dword_180025000
0x18001597b  mov     r9, rax
0x18001597e  cmp     edx, 5
0x180015981  jbe     loc_180015A53
0x180015987  mov     rax, cs:qword_180025018
0x18001598e  mov     r8, 400000000000h
0x180015998  mov     rdx, cs:qword_180025010
0x18001599f  test    r8, rdx
0x1800159a2  jz      loc_180015A53
0x1800159a8  mov     rcx, rax
0x1800159ab  and     rcx, r8
0x1800159ae  cmp     rcx, rax
0x1800159b1  jnz     loc_180015A53
0x1800159b7  lea     rax, [rbp+57h+var_78]
0x1800159bb  mov     [rbp+57h+var_78], 1000000h
0x1800159c3  mov     [rbp+57h+var_20], rax
0x1800159c7  xor     ecx, ecx
0x1800159c9  mov     [rbp+57h+var_80], ebx
0x1800159cc  lea     rax, [rbp+57h+var_80]
0x1800159d0  mov     [rbp+57h+var_30], rax
0x1800159d4  mov     [rbp+57h+var_7C], edi
0x1800159d7  mov     [rbp+57h+var_18], 8
0x1800159df  mov     [rbp+57h+var_28], 4
0x1800159e7  test    r9, r9
0x1800159ea  jz      short loc_180015A03
0x1800159ec  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800159f0  inc     rax
0x1800159f3  cmp     [r9+rax*2], cx
0x1800159f8  jnz     short loc_1800159F0
0x1800159fa  lea     eax, ds:2[rax*2]
0x180015a01  jmp     short loc_180015A0F
0x180015a03  lea     r9, dword_18001D6C4
0x180015a0a  mov     eax, 2
0x180015a0f  mov     [rbp+57h+var_38], eax
0x180015a12  lea     rdx, byte_180020F93; int
0x180015a19  lea     rax, [rbp+57h+var_7C]
0x180015a1d  mov     [rbp+57h+var_40], r9
0x180015a21  mov     [rbp+57h+var_50], rax
0x180015a25  xor     r9d, r9d; int
0x180015a28  lea     rax, [rbp+57h+var_70]
0x180015a2c  mov     [rbp+57h+var_34], ecx
0x180015a2f  mov     [rsp+0B0h+var_88], rax; PEVENT_DATA_DESCRIPTOR
0x180015a34  lea     rcx, dword_180025000; int
0x180015a3b  xor     r8d, r8d; int
0x180015a3e  mov     [rsp+0B0h+var_90], 6; ULONG
0x180015a46  mov     [rbp+57h+var_48], 4
0x180015a4e  call    _tlgWriteTransfer_EventWriteTransfer
0x180015a53  mov     rcx, [rbp+57h+var_10]
0x180015a57  xor     rcx, rsp; StackCookie
0x180015a5a  call    __security_check_cookie
0x180015a5f  lea     r11, [rsp+0B0h+var_s0]
0x180015a67  mov     rbx, [r11+10h]
0x180015a6b  mov     rdi, [r11+20h]
0x180015a6f  mov     rsp, r11
0x180015a72  pop     rbp
0x180015a73  retn
```
