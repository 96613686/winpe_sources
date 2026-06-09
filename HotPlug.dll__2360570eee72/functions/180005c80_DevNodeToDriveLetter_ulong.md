# DevNodeToDriveLetter(ulong)

- ea: `0x180005c80`
- end: `0x180005ee4`
- name: `?DevNodeToDriveLetter@@YAPEAGK@Z`
- size: `612`
- prototype: `unsigned __int16 *__fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x18000312c`

## callees

- `0x180002fd4`
- `0x180005c80`
- `0x180006004`
- `0x180008760`

## import_xrefs

- `msvcrt!wcschr` at `0x180005dba`
- `msvcrt!wcschr` at `0x180005dba`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180005dec`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180005e47`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180005dec`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180005e47`
- `KERNEL32!lstrcmpiW` at `0x180005e5b`
- `KERNEL32!lstrcmpiW` at `0x180005e5b`
- `KERNEL32!LocalFree` at `0x180005df7`
- `KERNEL32!LocalFree` at `0x180005eb8`
- `KERNEL32!LocalFree` at `0x180005df7`
- `KERNEL32!LocalFree` at `0x180005eb8`
- `KERNEL32!LocalAlloc` at `0x180005d1e`
- `KERNEL32!LocalAlloc` at `0x180005d84`
- `KERNEL32!LocalAlloc` at `0x180005d1e`
- `KERNEL32!LocalAlloc` at `0x180005d84`
- `USER32!LoadStringW` at `0x180005e97`
- `USER32!LoadStringW` at `0x180005e97`
- `CFGMGR32!CM_Get_Device_ID_ExW` at `0x180005cc8`
- `CFGMGR32!CM_Get_Device_ID_ExW` at `0x180005cc8`
- `CFGMGR32!CM_Get_Device_Interface_List_SizeW` at `0x180005cf5`
- `CFGMGR32!CM_Get_Device_Interface_List_SizeW` at `0x180005cf5`
- `CFGMGR32!CM_Get_Device_Interface_ListW` at `0x180005d49`
- `CFGMGR32!CM_Get_Device_Interface_ListW` at `0x180005d49`

## pseudocode

```c
unsigned __int16 *__fastcall DevNodeToDriveLetter(DEVINST a1)
{
  unsigned __int16 *v2; // r14
  WCHAR *v3; // rax
  unsigned __int16 *v4; // rdi
  __int64 v5; // rbx
  unsigned __int16 *v6; // rax
  WCHAR *v7; // rsi
  wchar_t *v8; // rbx
  wchar_t *v9; // rcx
  BOOL VolumeNameForVolumeMountPointW; // ebx
  ULONG pulLen; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR szVolumeMountPoint[4]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[200]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR szVolumeName[264]; // [rsp+1D0h] [rbp+D0h] BYREF
  WCHAR String2[264]; // [rsp+3E0h] [rbp+2E0h] BYREF
  WCHAR Source[264]; // [rsp+5F0h] [rbp+4F0h] BYREF

  pulLen = 0;
  if ( CM_Get_Device_ID_ExW(a1, Buffer, 0xC8u, 0, 0) )
    return 0;
  pulLen = 0;
  v2 = 0;
  if ( !CM_Get_Device_Interface_List_SizeW(&pulLen, &GUID_DEVINTERFACE_VOLUME, Buffer, 0) && pulLen > 1 )
  {
    v3 = (WCHAR *)LocalAlloc(0x40u, 2LL * pulLen);
    v4 = v3;
    if ( v3 )
    {
      if ( !CM_Get_Device_Interface_ListW(&GUID_DEVINTERFACE_VOLUME, Buffer, v3, pulLen, 0) )
      {
        if ( *v4 )
        {
          v5 = -1;
          v4[pulLen - 1] = 0;
          do
            ++v5;
          while ( v4[v5] );
          v6 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v5 + 4);
          v7 = v6;
          if ( v6 )
          {
            StringCchCopyW(v6, v5 + 1, v4);
            v8 = &v7[v5];
            *v8 = 0;
            v9 = wcschr(v7 + 4, 0x5Cu);
            if ( !v9 )
            {
              v9 = v8;
              *v8 = 92;
            }
            v9[1] = 0;
            szVolumeName[0] = 0;
            VolumeNameForVolumeMountPointW = GetVolumeNameForVolumeMountPointW(v7, szVolumeName, 0x104u);
            LocalFree(v7);
            if ( VolumeNameForVolumeMountPointW )
            {
              if ( szVolumeName[0] )
              {
                wcscpy(szVolumeMountPoint, L"A:\\");
                while ( 1 )
                {
                  String2[0] = 0;
                  GetVolumeNameForVolumeMountPointW(szVolumeMountPoint, String2, 0x104u);
                  if ( !lstrcmpiW(szVolumeName, String2) )
                    break;
                  if ( ++szVolumeMountPoint[0] > 0x5Au )
                    goto LABEL_21;
                }
                szVolumeMountPoint[2] = 0;
                if ( LoadStringW(hHotPlug, 0x460u, Source, 260) )
                  v2 = FormatString(Source, szVolumeMountPoint);
              }
            }
          }
        }
      }
LABEL_21:
      LocalFree(v4);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180005c80  push    rbp
0x180005c82  push    rbx
0x180005c83  push    rsi
0x180005c84  push    rdi
0x180005c85  push    r12
0x180005c87  push    r13
0x180005c89  push    r14
0x180005c8b  push    r15
0x180005c8d  lea     rbp, [rsp-718h]
0x180005c95  sub     rsp, 818h
0x180005c9c  mov     rax, cs:__security_cookie
0x180005ca3  xor     rax, rsp
0x180005ca6  mov     [rbp+750h+var_50], rax
0x180005cad  xor     r15d, r15d
0x180005cb0  lea     rdx, [rsp+850h+Buffer]; Buffer
0x180005cb5  xor     r9d, r9d; ulFlags
0x180005cb8  mov     [rsp+850h+pulLen], r15d
0x180005cbd  mov     r8d, 0C8h; BufferLen
0x180005cc3  mov     [rsp+850h+hMachine], r15; hMachine
0x180005cc8  call    cs:__imp_CM_Get_Device_ID_ExW
0x180005cce  test    eax, eax
0x180005cd0  jz      short loc_180005CD9
0x180005cd2  xor     eax, eax
0x180005cd4  jmp     loc_180005EC1
0x180005cd9  xor     r9d, r9d; ulFlags
0x180005cdc  mov     [rsp+850h+pulLen], r15d
0x180005ce1  lea     r8, [rsp+850h+Buffer]; pDeviceID
0x180005ce6  mov     r14, r15
0x180005ce9  lea     rdx, GUID_DEVINTERFACE_VOLUME; InterfaceClassGuid
0x180005cf0  lea     rcx, [rsp+850h+pulLen]; pulLen
0x180005cf5  call    cs:__imp_CM_Get_Device_Interface_List_SizeW
0x180005cfb  test    eax, eax
0x180005cfd  jnz     loc_180005EBE
0x180005d03  lea     r13d, [rax+1]
0x180005d07  cmp     [rsp+850h+pulLen], r13d
0x180005d0c  jbe     loc_180005EBE
0x180005d12  mov     edx, [rsp+850h+pulLen]
0x180005d16  lea     esi, [rax+40h]
0x180005d19  add     rdx, rdx; uBytes
0x180005d1c  mov     ecx, esi; uFlags
0x180005d1e  call    cs:__imp_LocalAlloc
0x180005d24  mov     rdi, rax
0x180005d27  test    rax, rax
0x180005d2a  jz      loc_180005EBE
0x180005d30  mov     r9d, [rsp+850h+pulLen]; BufferLen
0x180005d35  lea     rdx, [rsp+850h+Buffer]; pDeviceID
0x180005d3a  mov     r8, rax; Buffer
0x180005d3d  mov     dword ptr [rsp+850h+hMachine], r15d; ulFlags
0x180005d42  lea     rcx, GUID_DEVINTERFACE_VOLUME; InterfaceClassGuid
0x180005d49  call    cs:__imp_CM_Get_Device_Interface_ListW
0x180005d4f  test    eax, eax
0x180005d51  jnz     loc_180005EB5
0x180005d57  cmp     [rdi], r15w
0x180005d5b  jz      loc_180005EB5
0x180005d61  mov     eax, [rsp+850h+pulLen]
0x180005d65  dec     eax
0x180005d67  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005d6b  mov     [rdi+rax*2], r15w
0x180005d70  inc     rbx
0x180005d73  cmp     [rdi+rbx*2], r15w
0x180005d78  jnz     short loc_180005D70
0x180005d7a  lea     rdx, ds:4[rbx*2]; uBytes
0x180005d82  mov     ecx, esi; uFlags
0x180005d84  call    cs:__imp_LocalAlloc
0x180005d8a  mov     rsi, rax
0x180005d8d  test    rax, rax
0x180005d90  jz      loc_180005EB5
0x180005d96  lea     rdx, [rbx+1]; unsigned __int64
0x180005d9a  mov     r8, rdi; unsigned __int16 *
0x180005d9d  mov     rcx, rax; unsigned __int16 *
0x180005da0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005da5  mov     r12d, 5Ch ; '\'
0x180005dab  lea     rbx, [rsi+rbx*2]
0x180005daf  mov     edx, r12d; Ch
0x180005db2  mov     [rbx], r15w
0x180005db6  lea     rcx, [rsi+8]; Str
0x180005dba  call    cs:__imp_wcschr
0x180005dc0  mov     rcx, rax
0x180005dc3  test    rax, rax
0x180005dc6  jnz     short loc_180005DCF
0x180005dc8  mov     rcx, rbx
0x180005dcb  mov     [rbx], r12w
0x180005dcf  mov     [rcx+2], r15w
0x180005dd4  lea     rdx, [rbp+750h+szVolumeName]; lpszVolumeName
0x180005ddb  mov     rcx, rsi; lpszVolumeMountPoint
0x180005dde  mov     [rbp+750h+szVolumeName], r15w
0x180005de6  mov     r8d, 104h; cchBufferLength
0x180005dec  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180005df2  mov     rcx, rsi; hMem
0x180005df5  mov     ebx, eax
0x180005df7  call    cs:__imp_LocalFree
0x180005dfd  test    ebx, ebx
0x180005dff  jz      loc_180005EB5
0x180005e05  cmp     [rbp+750h+szVolumeName], r15w
0x180005e0d  jz      loc_180005EB5
0x180005e13  mov     eax, 41h ; 'A'
0x180005e18  mov     [rsp+850h+var_816], 5C003Ah
0x180005e20  mov     [rsp+850h+szVolumeMountPoint], ax
0x180005e25  mov     ebx, 104h
0x180005e2a  mov     [rsp+850h+var_812], r15w
0x180005e30  mov     r8d, ebx; cchBufferLength
0x180005e33  mov     [rbp+750h+String2], r15w
0x180005e3b  lea     rdx, [rbp+750h+String2]; lpszVolumeName
0x180005e42  lea     rcx, [rsp+850h+szVolumeMountPoint]; lpszVolumeMountPoint
0x180005e47  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180005e4d  lea     rdx, [rbp+750h+String2]; lpString2
0x180005e54  lea     rcx, [rbp+750h+szVolumeName]; lpString1
0x180005e5b  call    cs:__imp_lstrcmpiW
0x180005e61  test    eax, eax
0x180005e63  jz      short loc_180005E7B
0x180005e65  movzx   eax, [rsp+850h+szVolumeMountPoint]
0x180005e6a  add     ax, r13w
0x180005e6e  mov     [rsp+850h+szVolumeMountPoint], ax
0x180005e73  cmp     ax, 5Ah ; 'Z'
0x180005e77  jbe     short loc_180005E30
0x180005e79  jmp     short loc_180005EB5
0x180005e7b  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x180005e82  lea     r8, [rbp+750h+Source]; lpBuffer
0x180005e89  mov     r9d, ebx; cchBufferMax
0x180005e8c  mov     word ptr [rsp+850h+var_816+2], r15w
0x180005e92  mov     edx, 460h; uID
0x180005e97  call    cs:__imp_LoadStringW
0x180005e9d  test    eax, eax
0x180005e9f  jz      short loc_180005EB5
0x180005ea1  lea     rdx, [rsp+850h+szVolumeMountPoint]
0x180005ea6  lea     rcx, [rbp+750h+Source]; lpSource
0x180005ead  call    ?FormatString@@YAPEAGPEBGZZ; FormatString(ushort const *,...)
0x180005eb2  mov     r14, rax
0x180005eb5  mov     rcx, rdi; hMem
0x180005eb8  call    cs:__imp_LocalFree
0x180005ebe  mov     rax, r14
0x180005ec1  mov     rcx, [rbp+750h+var_50]
0x180005ec8  xor     rcx, rsp; StackCookie
0x180005ecb  call    __security_check_cookie
0x180005ed0  add     rsp, 818h
0x180005ed7  pop     r15
0x180005ed9  pop     r14
0x180005edb  pop     r13
0x180005edd  pop     r12
0x180005edf  pop     rdi
0x180005ee0  pop     rsi
0x180005ee1  pop     rbx
0x180005ee2  pop     rbp
0x180005ee3  retn
```
