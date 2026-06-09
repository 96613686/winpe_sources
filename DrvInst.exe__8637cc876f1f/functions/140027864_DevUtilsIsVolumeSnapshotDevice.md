# DevUtilsIsVolumeSnapshotDevice

- ea: `0x140027864`
- end: `0x1400279c6`
- name: `DevUtilsIsVolumeSnapshotDevice`
- size: `354`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012258`
- `0x140019700`
- `0x140021d84`

## callees

- `0x140027864`
- `0x140045f30`
- `0x140045fc0`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1400278b4`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1400278b4`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14002790e`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14002790e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002794d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002794d`

## pseudocode

```c
__int64 __fastcall DevUtilsIsVolumeSnapshotDevice(WCHAR *a1)
{
  unsigned int v1; // ebx
  unsigned int i; // esi
  const DEVPROPKEY *v3; // rdx
  const WCHAR *v4; // rdi
  __int64 v5; // rdx
  const WCHAR *v6; // rax
  ULONG PropertyBufferSize; // [rsp+30h] [rbp-D0h] BYREF
  DEVNODE pdnDevInst; // [rsp+34h] [rbp-CCh] BYREF
  DEVPROPTYPE PropertyType[1026]; // [rsp+38h] [rbp-C8h] BYREF

  pdnDevInst = 0;
  v1 = 0;
  PropertyType[0] = 0;
  PropertyBufferSize = 0;
  if ( !CM_Locate_DevNodeW(&pdnDevInst, a1, 1u) )
  {
    for ( i = 0; i < 2; ++i )
    {
      v3 = &DEVPKEY_Device_HardwareIds;
      v4 = (const WCHAR *)&PropertyType[512 * (unsigned __int64)i + 2];
      PropertyBufferSize = 2048;
      if ( i )
        v3 = &DEVPKEY_Device_CompatibleIds;
      v1 = 0;
      if ( !CM_Get_DevNode_PropertyW(
              pdnDevInst,
              v3,
              PropertyType,
              (PBYTE)&PropertyType[512 * (unsigned __int64)i + 2],
              &PropertyBufferSize,
              0)
        && PropertyType[0] == 8210 )
      {
        PropertyType[512 * (unsigned __int64)i + 513] = 0;
        while ( 1 )
        {
          v1 = 0;
          if ( !*v4 )
            break;
          if ( CompareStringOrdinal(L"STORAGE\\VolumeSnapshot", -1, v4, -1, 1) == 2 )
            return 1;
          v5 = 0x7FFFFFFF;
          v6 = v4;
          do
          {
            if ( !*v6 )
              break;
            ++v6;
            --v5;
          }
          while ( v5 );
          if ( !v5 )
            break;
          v4 += ((0x7FFFFFFF - v5) & -(__int64)(v5 != 0)) + 1;
        }
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x140027864  push    rbp
0x140027866  push    rbx
0x140027867  push    rsi
0x140027868  push    rdi
0x140027869  push    r14
0x14002786b  push    r15
0x14002786d  lea     rbp, [rsp-0F58h]
0x140027875  mov     eax, 1058h
0x14002787a  call    _alloca_probe
0x14002787f  sub     rsp, rax
0x140027882  mov     rax, cs:__security_cookie
0x140027889  xor     rax, rsp
0x14002788c  mov     [rbp+0F80h+var_40], rax
0x140027893  xor     r15d, r15d
0x140027896  mov     rdx, rcx; pDeviceID
0x140027899  lea     rcx, [rsp+1080h+pdnDevInst]; pdnDevInst
0x14002789e  mov     [rsp+1080h+pdnDevInst], r15d
0x1400278a3  mov     ebx, r15d
0x1400278a6  mov     [rsp+1080h+PropertyType], r15d
0x1400278ab  mov     [rsp+1080h+var_1050], r15d
0x1400278b0  lea     r8d, [r15+1]; ulFlags
0x1400278b4  call    cs:__imp_CM_Locate_DevNodeW
0x1400278ba  test    eax, eax
0x1400278bc  jnz     loc_1400279A5
0x1400278c2  mov     esi, r15d
0x1400278c5  mov     ecx, [rsp+1080h+pdnDevInst]; dnDevInst
0x1400278c9  lea     rax, DEVPKEY_Device_CompatibleIds
0x1400278d0  mov     r14d, esi
0x1400278d3  lea     rdi, [rsp+1080h+var_1040]
0x1400278d8  shl     r14, 0Bh
0x1400278dc  lea     rdx, DEVPKEY_Device_HardwareIds
0x1400278e3  add     rdi, r14
0x1400278e6  mov     [rsp+1080h+ulFlags], r15d; ulFlags
0x1400278eb  test    esi, esi
0x1400278ed  mov     [rsp+1080h+var_1050], 800h
0x1400278f5  mov     r9, rdi; PropertyBuffer
0x1400278f8  lea     r8, [rsp+1080h+PropertyType]; PropertyType
0x1400278fd  cmovnz  rdx, rax; PropertyKey
0x140027901  mov     ebx, r15d
0x140027904  lea     rax, [rsp+1080h+var_1050]
0x140027909  mov     [rsp+1080h+PropertyBufferSize], rax; PropertyBufferSize
0x14002790e  call    cs:__imp_CM_Get_DevNode_PropertyW
0x140027914  test    eax, eax
0x140027916  jnz     short loc_140027993
0x140027918  cmp     [rsp+1080h+PropertyType], 2012h
0x140027920  jnz     short loc_140027993
0x140027922  mov     [rbp+r14+0F80h+var_844], r15d
0x14002792a  mov     ebx, r15d
0x14002792d  cmp     [rdi], r15w
0x140027931  jz      short loc_140027993
0x140027933  or      eax, 0FFFFFFFFh
0x140027936  mov     dword ptr [rsp+1080h+PropertyBufferSize], 1; bIgnoreCase
0x14002793e  mov     r9d, eax; cchCount2
0x140027941  lea     rcx, String1; "STORAGE\\VolumeSnapshot"
0x140027948  mov     edx, eax; cchCount1
0x14002794a  mov     r8, rdi; lpString2
0x14002794d  call    cs:__imp_CompareStringOrdinal
0x140027953  cmp     eax, 2
0x140027956  jz      short loc_1400279A0
0x140027958  mov     edx, 7FFFFFFFh
0x14002795d  mov     rax, rdi
0x140027960  cmp     [rax], r15w
0x140027964  jz      short loc_140027970
0x140027966  add     rax, 2
0x14002796a  sub     rdx, 1
0x14002796e  jnz     short loc_140027960
0x140027970  mov     ecx, 7FFFFFFFh
0x140027975  mov     rax, rdx
0x140027978  sub     rcx, rdx
0x14002797b  neg     rax
0x14002797e  sbb     r8, r8
0x140027981  and     r8, rcx
0x140027984  test    rdx, rdx
0x140027987  jz      short loc_140027993
0x140027989  lea     rdi, [rdi+r8*2]
0x14002798d  add     rdi, 2
0x140027991  jmp     short loc_14002792A
0x140027993  inc     esi
0x140027995  cmp     esi, 2
0x140027998  jb      loc_1400278C5
0x14002799e  jmp     short loc_1400279A5
0x1400279a0  mov     ebx, 1
0x1400279a5  mov     eax, ebx
0x1400279a7  mov     rcx, [rbp+0F80h+var_40]
0x1400279ae  xor     rcx, rsp; StackCookie
0x1400279b1  call    __security_check_cookie
0x1400279b6  add     rsp, 1058h
0x1400279bd  pop     r15
0x1400279bf  pop     r14
0x1400279c1  pop     rdi
0x1400279c2  pop     rsi
0x1400279c3  pop     rbx
0x1400279c4  pop     rbp
0x1400279c5  retn
```
