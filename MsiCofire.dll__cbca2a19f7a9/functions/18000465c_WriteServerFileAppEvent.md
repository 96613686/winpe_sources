# WriteServerFileAppEvent

- ea: `0x18000465c`
- end: `0x180004804`
- name: `WriteServerFileAppEvent`
- size: `424`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800036f0`
- `0x1800038cc`

## callees

- `0x180002590`
- `0x18000465c`
- `0x180007040`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x1800047a8`
- `ADVAPI32!EventWrite` at `0x1800047a8`
- `ADVAPI32!EventRegister` at `0x1800046a8`
- `ADVAPI32!EventRegister` at `0x1800046a8`

## string_xrefs

- `0x1800047d4`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`
- `0x1800047cb`: `WriteServerFileAppEvent`

## pseudocode

```c
__int64 __fastcall WriteServerFileAppEvent(PCEVENT_DESCRIPTOR EventDescriptor, _WORD *a2, _WORD *a3)
{
  REGHANDLE v4; // rcx
  signed int v7; // eax
  unsigned int v8; // ebx
  int v9; // r9d
  __int64 v10; // r8
  __int64 v11; // rax
  signed int v12; // eax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-48h] BYREF
  _WORD *v15; // [rsp+40h] [rbp-38h]
  int v16; // [rsp+48h] [rbp-30h]
  int v17; // [rsp+4Ch] [rbp-2Ch]

  v4 = HServerEtwProvider;
  if ( !HServerEtwProvider )
  {
    v7 = EventRegister(&CFR_DM_ETW_PROVIDER, 0, 0, &HServerEtwProvider);
    v8 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      v9 = 60;
      goto LABEL_26;
    }
    v4 = HServerEtwProvider;
  }
  if ( EventDescriptor )
  {
    if ( a2 )
    {
      if ( *a2 )
      {
        if ( a3 )
        {
          if ( *a3 )
          {
            v10 = -1;
            UserData.Ptr = (ULONGLONG)a2;
            v11 = -1;
            v8 = 0;
            do
              ++v11;
            while ( a2[v11] );
            UserData.Reserved = 0;
            UserData.Size = 2 * v11 + 2;
            v15 = a3;
            do
              ++v10;
            while ( a3[v10] );
            v17 = 0;
            v16 = 2 * v10 + 2;
            v12 = EventWrite(v4, EventDescriptor, 2u, &UserData);
            if ( v12 )
            {
              if ( v12 > 0 )
                v8 = (unsigned __int16)v12 | 0x80070000;
              else
                v8 = v12;
              v9 = 84;
LABEL_26:
              DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "WriteServerFileAppEvent", v9, v8);
            }
          }
          else
          {
            v8 = -2147024809;
            DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "WriteServerFileAppEvent", 67, -2147024809);
          }
        }
        else
        {
          v8 = -2147024809;
          DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "WriteServerFileAppEvent", 66, -2147024809);
        }
      }
      else
      {
        v8 = -2147024809;
        DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "WriteServerFileAppEvent", 65, -2147024809);
      }
    }
    else
    {
      v8 = -2147024809;
      DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "WriteServerFileAppEvent", 64, -2147024809);
    }
  }
  else
  {
    v8 = -2147024809;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "WriteServerFileAppEvent", 63, -2147024809);
  }
  return v8;
}

```

## disassembly

```asm
0x18000465c  mov     [rsp+arg_8], rbx
0x180004661  mov     [rsp+arg_10], rbp
0x180004666  push    rsi
0x180004667  push    rdi
0x180004668  push    r14
0x18000466a  sub     rsp, 60h
0x18000466e  mov     rax, cs:__security_cookie
0x180004675  xor     rax, rsp
0x180004678  mov     [rsp+78h+var_28], rax
0x18000467d  mov     rbp, rcx
0x180004680  xor     r14d, r14d
0x180004683  mov     rcx, cs:HServerEtwProvider
0x18000468a  mov     rsi, r8
0x18000468d  mov     rdi, rdx
0x180004690  test    rcx, rcx
0x180004693  jnz     short loc_1800046D1
0x180004695  lea     r9, HServerEtwProvider; RegHandle
0x18000469c  xor     r8d, r8d; CallbackContext
0x18000469f  xor     edx, edx; EnableCallback
0x1800046a1  lea     rcx, CFR_DM_ETW_PROVIDER; ProviderId
0x1800046a8  call    cs:__imp_EventRegister
0x1800046ae  mov     ebx, eax
0x1800046b0  test    eax, eax
0x1800046b2  jz      short loc_1800046CA
0x1800046b4  jle     short loc_1800046BF
0x1800046b6  movzx   ebx, ax
0x1800046b9  or      ebx, 80070000h
0x1800046bf  mov     r9d, 3Ch ; '<'
0x1800046c5  jmp     loc_1800047C7
0x1800046ca  mov     rcx, cs:HServerEtwProvider; RegHandle
0x1800046d1  test    rbp, rbp
0x1800046d4  jnz     short loc_1800046EA
0x1800046d6  mov     eax, 80070057h
0x1800046db  lea     r9d, [rbp+3Fh]
0x1800046df  mov     ebx, eax
0x1800046e1  mov     [rsp+78h+var_58], eax
0x1800046e5  jmp     loc_1800047CB
0x1800046ea  test    rdi, rdi
0x1800046ed  jnz     short loc_180004703
0x1800046ef  mov     eax, 80070057h
0x1800046f4  lea     r9d, [rdi+40h]
0x1800046f8  mov     ebx, eax
0x1800046fa  mov     [rsp+78h+var_58], eax
0x1800046fe  jmp     loc_1800047CB
0x180004703  cmp     [rdi], r14w
0x180004707  jnz     short loc_18000471F
0x180004709  mov     eax, 80070057h
0x18000470e  mov     r9d, 41h ; 'A'
0x180004714  mov     ebx, eax
0x180004716  mov     [rsp+78h+var_58], eax
0x18000471a  jmp     loc_1800047CB
0x18000471f  test    rsi, rsi
0x180004722  jnz     short loc_180004738
0x180004724  mov     eax, 80070057h
0x180004729  lea     r9d, [rsi+42h]
0x18000472d  mov     ebx, eax
0x18000472f  mov     [rsp+78h+var_58], eax
0x180004733  jmp     loc_1800047CB
0x180004738  cmp     [rsi], r14w
0x18000473c  jnz     short loc_180004751
0x18000473e  mov     eax, 80070057h
0x180004743  mov     r9d, 43h ; 'C'
0x180004749  mov     ebx, eax
0x18000474b  mov     [rsp+78h+var_58], eax
0x18000474f  jmp     short loc_1800047CB
0x180004751  or      r8, 0FFFFFFFFFFFFFFFFh
0x180004755  mov     [rsp+78h+UserData.Ptr], rdi
0x18000475a  mov     rax, r8
0x18000475d  mov     ebx, r14d
0x180004760  inc     rax
0x180004763  cmp     [rdi+rax*2], r14w
0x180004768  jnz     short loc_180004760
0x18000476a  lea     eax, ds:2[rax*2]
0x180004771  mov     dword ptr [rsp+78h+UserData.0Ch], r14d
0x180004776  mov     [rsp+78h+UserData.Size], eax
0x18000477a  mov     [rsp+78h+var_38], rsi
0x18000477f  inc     r8
0x180004782  cmp     [rsi+r8*2], r14w
0x180004787  jnz     short loc_18000477F
0x180004789  lea     eax, ds:2[r8*2]
0x180004791  mov     [rsp+78h+var_2C], r14d
0x180004796  mov     r8d, 2; UserDataCount
0x18000479c  mov     [rsp+78h+var_30], eax
0x1800047a0  lea     r9, [rsp+78h+UserData]; UserData
0x1800047a5  mov     rdx, rbp; EventDescriptor
0x1800047a8  call    cs:__imp_EventWrite
0x1800047ae  test    eax, eax
0x1800047b0  jz      short loc_1800047E0
0x1800047b2  jg      short loc_1800047B8
0x1800047b4  mov     ebx, eax
0x1800047b6  jmp     short loc_1800047C1
0x1800047b8  movzx   ebx, ax
0x1800047bb  or      ebx, 80070000h
0x1800047c1  mov     r9d, 54h ; 'T'
0x1800047c7  mov     [rsp+78h+var_58], ebx
0x1800047cb  lea     r8, aWriteserverfil_0; "WriteServerFileAppEvent"
0x1800047d2  xor     ecx, ecx; Level
0x1800047d4  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x1800047db  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x1800047e0  mov     eax, ebx
0x1800047e2  mov     rcx, [rsp+78h+var_28]
0x1800047e7  xor     rcx, rsp; StackCookie
0x1800047ea  call    __security_check_cookie
0x1800047ef  lea     r11, [rsp+78h+var_18]
0x1800047f4  mov     rbx, [r11+28h]
0x1800047f8  mov     rbp, [r11+30h]
0x1800047fc  mov     rsp, r11
0x1800047ff  pop     r14
0x180004801  pop     rdi
0x180004802  pop     rsi
0x180004803  retn
```
