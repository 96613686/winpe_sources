# CommonUtil::StoreRpcGetClientPidFunction(int)

- ea: `0x140003ed8`
- end: `0x140003f6a`
- name: `?StoreRpcGetClientPidFunction@CommonUtil@@YAJH@Z`
- size: `146`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001e068`

## callees

- `0x1400039e4`
- `0x140003ed8`
- `0x14001da70`

## string_xrefs

- `0x140003efc`: `rpcrt4.dll`

## pseudocode

```c
__int64 __fastcall CommonUtil::StoreRpcGetClientPidFunction(CommonUtil *this, __int64 a2, __int64 a3, const char *a4)
{
  int v4; // edi
  int EncodedProcAddress; // eax
  unsigned int v6; // ebx

  v4 = (int)this;
  dword_14003C120 = 0;
  EncodedProcAddress = CommonUtil::UtilGetEncodedProcAddress(
                         (CommonUtil *)&qword_14003C118,
                         (void **)L"rpcrt4.dll",
                         "I_RpcBindingInqLocalClientPID",
                         a4);
  v6 = EncodedProcAddress;
  if ( EncodedProcAddress == -2147024769 )
    return 0;
  if ( EncodedProcAddress >= 0 )
  {
    if ( !v4 )
      dword_14003C120 = 1;
    return 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_5d796bf5d6913099feb0f367352bb89a_Traceguids,
      (unsigned int)EncodedProcAddress);
  return v6;
}

```

## disassembly

```asm
0x140003ed8  mov     [rsp+arg_0], rbx
0x140003edd  push    rdi
0x140003ede  sub     rsp, 20h
0x140003ee2  mov     edi, ecx
0x140003ee4  mov     cs:dword_14003C120, 0
0x140003eee  lea     rcx, qword_14003C118; this
0x140003ef5  lea     r8, aIRpcbindinginq; "I_RpcBindingInqLocalClientPID"
0x140003efc  lea     rdx, aRpcrt4Dll_0; "rpcrt4.dll"
0x140003f03  call    ?UtilGetEncodedProcAddress@CommonUtil@@YAJPEAPEAXPEB_WPEBD@Z; CommonUtil::UtilGetEncodedProcAddress(void * *,wchar_t const *,char const *)
0x140003f08  mov     ebx, eax
0x140003f0a  cmp     eax, 8007007Fh
0x140003f0f  jz      short loc_140003F5D
0x140003f11  mov     edx, eax
0x140003f13  shr     edx, 1Fh
0x140003f16  test    dl, dl
0x140003f18  jz      short loc_140003F4F
0x140003f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f21  lea     rax, WPP_GLOBAL_Control
0x140003f28  cmp     rcx, rax
0x140003f2b  jz      short loc_140003F4B
0x140003f2d  test    byte ptr [rcx+1Ch], 1
0x140003f31  jz      short loc_140003F4B
0x140003f33  mov     rcx, [rcx+10h]
0x140003f37  lea     r8, WPP_5d796bf5d6913099feb0f367352bb89a_Traceguids
0x140003f3e  mov     edx, 0Ah
0x140003f43  mov     r9d, ebx
0x140003f46  call    WPP_SF_d
0x140003f4b  mov     eax, ebx
0x140003f4d  jmp     short loc_140003F5F
0x140003f4f  test    edi, edi
0x140003f51  jnz     short loc_140003F5D
0x140003f53  mov     cs:dword_14003C120, 1
0x140003f5d  xor     eax, eax
0x140003f5f  mov     rbx, [rsp+28h+arg_0]
0x140003f64  add     rsp, 20h
0x140003f68  pop     rdi
0x140003f69  retn
```
