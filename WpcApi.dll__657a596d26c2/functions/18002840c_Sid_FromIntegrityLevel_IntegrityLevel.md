# Sid::FromIntegrityLevel(IntegrityLevel)

- ea: `0x18002840c`
- end: `0x1800284af`
- name: `?FromIntegrityLevel@Sid@@SA?AV1@W4IntegrityLevel@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027bd4`

## callees

- `0x180003d20`
- `0x18000b29c`
- `0x1800195c4`
- `0x18002840c`
- `0x1800286e8`

## pseudocode

```c
__int64 __fastcall Sid::FromIntegrityLevel(__int64 a1, unsigned int a2)
{
  const wchar_t *v3; // rdx
  _BYTE pExceptionObject[48]; // [rsp+28h] [rbp-30h] BYREF

  if ( a2 )
  {
    switch ( a2 )
    {
      case 1u:
        v3 = L"S-1-16-8192";
        break;
      case 2u:
        v3 = L"S-1-16-8193";
        break;
      case 3u:
        v3 = L"S-1-16-12288";
        break;
      default:
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids, a2);
        ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147024809);
        throw (ErrorCodeException *)pExceptionObject;
    }
  }
  else
  {
    v3 = L"S-1-16-4096";
  }
  Sid::FromString(a1, v3);
  return a1;
}

```

## disassembly

```asm
0x18002840c  push    rbx
0x18002840e  sub     rsp, 50h
0x180028412  mov     rbx, rcx
0x180028415  mov     ecx, edx
0x180028417  mov     r9d, edx
0x18002841a  test    edx, edx
0x18002841c  jz      short loc_180028448
0x18002841e  sub     ecx, 1
0x180028421  jz      short loc_18002843F
0x180028423  sub     ecx, 1
0x180028426  jz      short loc_180028436
0x180028428  cmp     ecx, 1
0x18002842b  jnz     short loc_180028460
0x18002842d  lea     rdx, aS11612288; "S-1-16-12288"
0x180028434  jmp     short loc_18002844F
0x180028436  lea     rdx, aS1168193; "S-1-16-8193"
0x18002843d  jmp     short loc_18002844F
0x18002843f  lea     rdx, aS1168192; "S-1-16-8192"
0x180028446  jmp     short loc_18002844F
0x180028448  lea     rdx, aS1164096; "S-1-16-4096"
0x18002844f  mov     rcx, rbx
0x180028452  call    ?FromString@Sid@@SA?AV1@PEBG@Z; Sid::FromString(ushort const *)
0x180028457  mov     rax, rbx
0x18002845a  add     rsp, 50h
0x18002845e  pop     rbx
0x18002845f  retn
0x180028460  mov     rcx, cs:WPP_GLOBAL_Control
0x180028467  lea     rax, WPP_GLOBAL_Control
0x18002846e  cmp     rcx, rax
0x180028471  jz      short loc_18002848E
0x180028473  test    byte ptr [rcx+1Ch], 1
0x180028477  jz      short loc_18002848E
0x180028479  mov     rcx, [rcx+10h]
0x18002847d  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x180028484  mov     edx, 16h
0x180028489  call    WPP_SF_d
0x18002848e  mov     edx, 80070057h; int
0x180028493  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180028498  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18002849d  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1800284a4  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800284a9  call    _CxxThrowException_0
```
