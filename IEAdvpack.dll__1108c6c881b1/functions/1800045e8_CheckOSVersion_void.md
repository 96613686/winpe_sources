# CheckOSVersion(void)

- ea: `0x1800045e8`
- end: `0x1800046f9`
- name: `?CheckOSVersion@@YAHXZ`
- size: `273`
- prototype: `__int64(void)`
- caller_count: `12`
- callee_count: `4`
- tags: ``

## callers

- `0x180002450`
- `0x180003a5c`
- `0x180004754`
- `0x1800067dc`
- `0x180006d24`
- `0x180006e54`
- `0x1800071c0`
- `0x180007454`
- `0x18000bc50`
- `0x18000bc80`
- `0x18000bdb0`
- `0x1800171b0`

## callees

- `0x1800045e8`
- `0x180008a6c`
- `0x18001b94e`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetVersionExW` at `0x180004620`
- `KERNEL32!GetVersionExW` at `0x180004620`

## pseudocode

```c
__int64 CheckOSVersion(void)
{
  UINT v0; // edx
  __int64 result; // rax
  _OSVERSIONINFOW VersionInformation; // [rsp+30h] [rbp-138h] BYREF

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
  VersionInformation.dwOSVersionInfoSize = 276;
  if ( !GetVersionExW(&VersionInformation) )
  {
    v0 = 1101;
LABEL_3:
    MsgBox2Param(hWnd, v0, 0, 0, 0x10u, 0);
    return 0;
  }
  if ( VersionInformation.dwPlatformId == 1 )
  {
    result = 1;
    ctx = 0;
    dword_1800257E0 = 1;
  }
  else
  {
    if ( VersionInformation.dwPlatformId != 2 )
    {
      v0 = 1111;
      goto LABEL_3;
    }
    result = 1;
    dword_1800257E0 = 1;
    ctx = 2;
    if ( VersionInformation.dwMajorVersion > 3 )
    {
      if ( VersionInformation.dwMajorVersion == 5 )
      {
        if ( !VersionInformation.dwMinorVersion )
        {
          ctx = 3;
          return result;
        }
      }
      else if ( VersionInformation.dwMajorVersion <= 5 )
      {
        return result;
      }
      ctx = 4;
    }
    else
    {
      ctx = 1;
      if ( VersionInformation.dwMajorVersion < 3 || VersionInformation.dwMinorVersion < 0x33 )
        dword_1800257E0 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800045e8  sub     rsp, 168h
0x1800045ef  mov     rax, cs:__security_cookie
0x1800045f6  xor     rax, rsp
0x1800045f9  mov     [rsp+168h+var_18], rax
0x180004601  xor     edx, edx; Val
0x180004603  lea     rcx, [rsp+168h+VersionInformation.dwMajorVersion]; void *
0x180004608  mov     r8d, 110h; Size
0x18000460e  call    memset_0
0x180004613  lea     rcx, [rsp+168h+VersionInformation]; lpVersionInformation
0x180004618  mov     [rsp+168h+VersionInformation.dwOSVersionInfoSize], 114h
0x180004620  call    cs:__imp_GetVersionExW
0x180004626  xor     r8d, r8d; unsigned __int16 *
0x180004629  test    eax, eax
0x18000462b  jnz     short loc_180004655
0x18000462d  mov     edx, 44Dh; uID
0x180004632  mov     rcx, cs:hWnd; hWnd
0x180004639  xor     r9d, r9d; unsigned __int16 *
0x18000463c  mov     [rsp+168h+var_140], r8d; unsigned int
0x180004641  mov     [rsp+168h+var_148], 10h; unsigned int
0x180004649  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x18000464e  xor     eax, eax
0x180004650  jmp     loc_1800046E1
0x180004655  mov     eax, [rsp+168h+VersionInformation.dwPlatformId]
0x180004659  sub     eax, 1
0x18000465c  jz      short loc_1800046CE
0x18000465e  cmp     eax, 1
0x180004661  jz      short loc_18000466A
0x180004663  mov     edx, 457h
0x180004668  jmp     short loc_180004632
0x18000466a  mov     eax, 1
0x18000466f  mov     cs:dword_1800257E0, eax
0x180004675  lea     ecx, [rax+1]
0x180004678  mov     cs:?ctx@@3UADVCONTEXTW@@A, cx; ADVCONTEXTW ctx
0x18000467f  lea     r9d, [rax+2]
0x180004683  mov     ecx, [rsp+168h+VersionInformation.dwMajorVersion]
0x180004687  cmp     ecx, r9d
0x18000468a  ja      short loc_1800046A7
0x18000468c  mov     cs:?ctx@@3UADVCONTEXTW@@A, ax; ADVCONTEXTW ctx
0x180004693  jb      short loc_18000469E
0x180004695  jnz     short loc_1800046E1
0x180004697  cmp     [rsp+168h+VersionInformation.dwMinorVersion], 33h ; '3'
0x18000469c  jnb     short loc_1800046E1
0x18000469e  mov     cs:dword_1800257E0, r8d
0x1800046a5  jmp     short loc_1800046E1
0x1800046a7  cmp     ecx, 5
0x1800046aa  jnz     short loc_1800046BE
0x1800046ac  mov     edx, [rsp+168h+VersionInformation.dwMinorVersion]
0x1800046b0  test    edx, edx
0x1800046b2  jnz     short loc_1800046C0
0x1800046b4  mov     cs:?ctx@@3UADVCONTEXTW@@A, r9w; ADVCONTEXTW ctx
0x1800046bc  jmp     short loc_1800046E1
0x1800046be  jbe     short loc_1800046E1
0x1800046c0  mov     ecx, 4
0x1800046c5  mov     cs:?ctx@@3UADVCONTEXTW@@A, cx; ADVCONTEXTW ctx
0x1800046cc  jmp     short loc_1800046E1
0x1800046ce  mov     eax, 1
0x1800046d3  mov     cs:?ctx@@3UADVCONTEXTW@@A, r8w; ADVCONTEXTW ctx
0x1800046db  mov     cs:dword_1800257E0, eax
0x1800046e1  mov     rcx, [rsp+168h+var_18]
0x1800046e9  xor     rcx, rsp; StackCookie
0x1800046ec  call    __security_check_cookie
0x1800046f1  add     rsp, 168h
0x1800046f8  retn
```
