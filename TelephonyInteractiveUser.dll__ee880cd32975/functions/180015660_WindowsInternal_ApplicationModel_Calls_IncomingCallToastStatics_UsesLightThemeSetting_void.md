# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_UsesLightThemeSetting(void)

- ea: `0x180015660`
- end: `0x180015740`
- name: `?_UsesLightThemeSetting@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAHXZ`
- size: `224`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001dc0`
- `0x180015660`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800156b8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800156b8`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_UsesLightThemeSetting(
        WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *this)
{
  unsigned int v1; // ebx
  LSTATUS ValueW; // eax
  signed int v3; // ecx
  __int64 result; // rax
  unsigned int v5; // [rsp+40h] [rbp-28h] BYREF
  DWORD v6; // [rsp+44h] [rbp-24h] BYREF
  DWORD v7; // [rsp+48h] [rbp-20h] BYREF

  v7 = 4;
  v1 = 0;
  v6 = 0;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Themes\\Personalize",
             L"SystemUsesLightTheme",
             0x10000012u,
             &v6,
             &v5,
             &v7);
  v3 = ValueW;
  if ( ValueW )
  {
    if ( ValueW == 234 )
    {
      LOWORD(v3) = 13;
    }
    else if ( ValueW <= 0 )
    {
      goto LABEL_12;
    }
  }
  else
  {
    LOWORD(v3) = 13;
    if ( v6 == 4 )
    {
      if ( v5 <= 1 )
      {
        v3 = 0;
        LOBYTE(v1) = v5 == 1;
        goto LABEL_12;
      }
    }
    else if ( v7 == 4 && (unsigned __int16)(v5 - 48) <= 1u )
    {
      LOBYTE(v1) = (_WORD)v5 == 49;
      v3 = 0;
      goto LABEL_12;
    }
  }
  v3 = (unsigned __int16)v3 | 0x80070000;
LABEL_12:
  result = 0;
  if ( v3 >= 0 )
    return v1;
  return result;
}

```

## disassembly

```asm
0x180015660  mov     r11, rsp
0x180015663  push    rbx
0x180015664  sub     rsp, 60h
0x180015668  mov     rax, cs:__security_cookie
0x18001566f  xor     rax, rsp
0x180015672  mov     [rsp+68h+var_18], rax
0x180015677  lea     rax, [r11-20h]
0x18001567b  mov     [rsp+68h+var_20], 4
0x180015683  mov     [r11-38h], rax
0x180015687  lea     r8, Value; "SystemUsesLightTheme"
0x18001568e  lea     rax, [r11-28h]
0x180015692  xor     ebx, ebx
0x180015694  mov     [r11-40h], rax
0x180015698  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001569f  lea     rax, [r11-24h]
0x1800156a3  mov     [rsp+68h+var_24], ebx
0x1800156a7  mov     r9d, 10000012h; dwFlags
0x1800156ad  mov     [r11-48h], rax
0x1800156b1  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800156b8  call    cs:__imp_RegGetValueW
0x1800156be  mov     ecx, eax
0x1800156c0  test    eax, eax
0x1800156c2  jnz     short loc_18001570B
0x1800156c4  cmp     [rsp+68h+var_24], 4
0x1800156c9  lea     ecx, [rbx+0Dh]
0x1800156cc  jnz     short loc_1800156E2
0x1800156ce  lea     edx, [rbx+1]
0x1800156d1  cmp     [rsp+68h+var_28], edx
0x1800156d5  ja      short loc_18001571D
0x1800156d7  xor     ecx, ecx
0x1800156d9  cmp     [rsp+68h+var_28], edx
0x1800156dd  setz    bl
0x1800156e0  jmp     short loc_180015726
0x1800156e2  cmp     [rsp+68h+var_20], 4
0x1800156e7  jnz     short loc_18001571D
0x1800156e9  movzx   eax, word ptr [rsp+68h+var_28]
0x1800156ee  mov     edx, 1
0x1800156f3  sub     ax, 30h ; '0'
0x1800156f7  cmp     ax, dx
0x1800156fa  ja      short loc_18001571D
0x1800156fc  lea     eax, [rdx+30h]
0x1800156ff  cmp     ax, word ptr [rsp+68h+var_28]
0x180015704  setz    bl
0x180015707  xor     ecx, ecx
0x180015709  jmp     short loc_180015726
0x18001570b  cmp     eax, 0EAh
0x180015710  jnz     short loc_180015719
0x180015712  mov     ecx, 0Dh
0x180015717  jmp     short loc_18001571D
0x180015719  test    eax, eax
0x18001571b  jle     short loc_180015726
0x18001571d  movzx   ecx, cx
0x180015720  or      ecx, 80070000h
0x180015726  xor     eax, eax
0x180015728  test    ecx, ecx
0x18001572a  cmovns  eax, ebx
0x18001572d  mov     rcx, [rsp+68h+var_18]
0x180015732  xor     rcx, rsp; StackCookie
0x180015735  call    __security_check_cookie
0x18001573a  add     rsp, 60h
0x18001573e  pop     rbx
0x18001573f  retn
```
