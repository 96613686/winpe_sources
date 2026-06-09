# Microsoft::Bluetooth::Profiles::MediaControl::Interface::SessionAumidFromAppSourceId(ushort *)

- ea: `0x18004dca0`
- end: `0x18004dd61`
- name: `?SessionAumidFromAppSourceId@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@YAPEAUHSTRING__@@PEAG@Z`
- size: `193`
- prototype: `HSTRING __fastcall(Microsoft::Bluetooth::Profiles::MediaControl::Interface *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004e0cc`

## callees

- `0x180001dd0`
- `0x180044c68`
- `0x18004dca0`
- `0x18004e858`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004dd35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004dd35`

## pseudocode

```c
HSTRING __fastcall Microsoft::Bluetooth::Profiles::MediaControl::Interface::SessionAumidFromAppSourceId(
        Microsoft::Bluetooth::Profiles::MediaControl::Interface *this,
        unsigned __int16 *a2)
{
  unsigned __int64 v3; // r8
  __int64 v4; // rcx
  __int64 i; // rax
  UINT32 v6; // edx
  const WCHAR *v7; // rcx
  unsigned __int64 v9; // [rsp+20h] [rbp-158h]
  UINT32 length[2]; // [rsp+30h] [rbp-148h] BYREF
  HSTRING string; // [rsp+38h] [rbp-140h] BYREF
  unsigned __int16 v12[72]; // [rsp+40h] [rbp-138h] BYREF
  unsigned __int16 v13[72]; // [rsp+D0h] [rbp-A8h] BYREF

  string = 0;
  if ( !this )
    return 0;
  *(_QWORD *)length = 0;
  if ( (int)StringCchLengthW((const unsigned __int16 *)this, 0x7FFFFFFFu, (unsigned __int64 *)length) < 0 )
    return 0;
  if ( ParseAppUserModelId((const unsigned __int16 *)this, v13, v3, v12, v9) >= 0 )
  {
    v6 = length[0];
    v7 = (const WCHAR *)this;
  }
  else
  {
    v4 = 0;
    for ( i = *(_QWORD *)length - 1LL; i; --i )
    {
      if ( *((_WORD *)this + i - 1) == 92 )
      {
        v4 = i;
        break;
      }
    }
    v6 = length[0] - v4;
    v7 = (const WCHAR *)((char *)this + 2 * v4);
  }
  if ( WindowsCreateString(v7, v6, &string) >= 0 )
    return string;
  else
    return 0;
}

```

## disassembly

```asm
0x18004dca0  push    rbx
0x18004dca2  sub     rsp, 170h
0x18004dca9  mov     rax, cs:__security_cookie
0x18004dcb0  xor     rax, rsp
0x18004dcb3  mov     [rsp+178h+var_18], rax
0x18004dcbb  mov     [rsp+178h+string], 0
0x18004dcc4  mov     rbx, rcx
0x18004dcc7  test    rcx, rcx
0x18004dcca  jz      short loc_18004DD46
0x18004dccc  lea     r8, [rsp+178h+length]; unsigned __int64 *
0x18004dcd1  mov     qword ptr [rsp+178h+length], 0
0x18004dcda  mov     edx, 7FFFFFFFh; unsigned __int64
0x18004dcdf  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004dce4  test    eax, eax
0x18004dce6  js      short loc_18004DD46
0x18004dce8  lea     r9, [rsp+178h+var_138]; unsigned __int16 *
0x18004dced  mov     rcx, rbx; unsigned __int16 *
0x18004dcf0  lea     rdx, [rsp+178h+var_A8]; unsigned __int16 *
0x18004dcf8  call    ?ParseAppUserModelId@@YAJPEBGPEAG_K12@Z; ParseAppUserModelId(ushort const *,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x18004dcfd  test    eax, eax
0x18004dcff  jns     short loc_18004DD29
0x18004dd01  mov     rdx, qword ptr [rsp+178h+length]
0x18004dd06  xor     ecx, ecx
0x18004dd08  lea     rax, [rdx-1]
0x18004dd0c  test    rax, rax
0x18004dd0f  jz      short loc_18004DD21
0x18004dd11  cmp     word ptr [rbx+rax*2-2], 5Ch ; '\'
0x18004dd17  jz      short loc_18004DD1E
0x18004dd19  dec     rax
0x18004dd1c  jmp     short loc_18004DD0C
0x18004dd1e  mov     rcx, rax
0x18004dd21  sub     edx, ecx
0x18004dd23  lea     rcx, [rbx+rcx*2]
0x18004dd27  jmp     short loc_18004DD30
0x18004dd29  mov     edx, [rsp+178h+length]; length
0x18004dd2d  mov     rcx, rbx; sourceString
0x18004dd30  lea     r8, [rsp+178h+string]; string
0x18004dd35  call    cs:__imp_WindowsCreateString
0x18004dd3b  test    eax, eax
0x18004dd3d  js      short loc_18004DD46
0x18004dd3f  mov     rax, [rsp+178h+string]
0x18004dd44  jmp     short loc_18004DD48
0x18004dd46  xor     eax, eax
0x18004dd48  mov     rcx, [rsp+178h+var_18]
0x18004dd50  xor     rcx, rsp; StackCookie
0x18004dd53  call    __security_check_cookie
0x18004dd58  add     rsp, 170h
0x18004dd5f  pop     rbx
0x18004dd60  retn
```
