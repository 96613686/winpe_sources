# DMGetClientHardwareUID(ushort * *,int)

- ea: `0x18005fc60`
- end: `0x18005fdca`
- name: `?DMGetClientHardwareUID@@YAJPEAPEAGH@Z`
- size: `362`
- prototype: `__int64 __fastcall(unsigned __int16 **, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180007270`
- `0x18005d690`
- `0x18005fc60`
- `0x18005fe70`
- `0x18005fef4`
- `0x180060040`
- `0x180060360`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005fce0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005fce0`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18005fcc5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18005fcc5`

## pseudocode

```c
int __fastcall DMGetClientHardwareUID(unsigned __int16 **a1, int a2)
{
  int result; // eax
  unsigned __int16 *v4; // rax
  _WORD *v5; // r9
  unsigned int v6; // edx
  __int64 v7; // rax
  __int64 v8; // r8
  unsigned int v9; // [rsp+20h] [rbp-28h] BYREF
  GUID pguid; // [rsp+28h] [rbp-20h] BYREF

  if ( !a1 )
    return -2147024809;
  if ( a2 || (result = GetOfflineHardwareUID(a1), result < 0) )
  {
    result = GetPhoneUID(a1);
    if ( result < 0 )
    {
      result = GetClientMDMID(a1);
      if ( result < 0 )
      {
        pguid = 0;
        result = CoCreateGuid(&pguid);
        if ( result >= 0 )
        {
          v4 = (unsigned __int16 *)LocalAlloc(0, 0x44u);
          *a1 = v4;
          if ( v4 )
          {
            v9 = 0;
            result = ULongLongToULong(0x20u, &v9);
            if ( result >= 0 )
            {
              if ( v9 + 1 >= v9 )
              {
                if ( v9 + 1 > 0x22 )
                  return -2147024809;
                v6 = 1;
                do
                {
                  v7 = v6 - 1;
                  v8 = v6++;
                  *v5 = a0123456789abcd_0[(unsigned __int64)*((unsigned __int8 *)&pguid.Data1 + v7) >> 4];
                  v5 += 2;
                  *(v5 - 1) = a0123456789abcd_0[*((_BYTE *)&pguid.Data1 + v7) & 0xF];
                }
                while ( v6 != 16 );
                *v5 = a0123456789abcd_0[(unsigned __int64)*((unsigned __int8 *)&pguid.Data1 + v8) >> 4];
                v5[1] = a0123456789abcd_0[*((_BYTE *)&pguid.Data1 + v8) & 0xF];
                v5[2] = 0;
                return DMSetDeviceClientID(*a1);
              }
              else
              {
                return -2147024362;
              }
            }
          }
          else
          {
            return -2147024882;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005fc60  push    rbx
0x18005fc62  sub     rsp, 40h
0x18005fc66  mov     rax, cs:__security_cookie
0x18005fc6d  xor     rax, rsp
0x18005fc70  mov     [rsp+48h+var_10], rax
0x18005fc75  mov     rbx, rcx
0x18005fc78  test    rcx, rcx
0x18005fc7b  jnz     short loc_18005FC87
0x18005fc7d  mov     eax, 80070057h
0x18005fc82  jmp     loc_18005FDB6
0x18005fc87  test    edx, edx
0x18005fc89  jnz     short loc_18005FC98
0x18005fc8b  call    GetOfflineHardwareUID
0x18005fc90  test    eax, eax
0x18005fc92  jns     loc_18005FDB6
0x18005fc98  mov     rcx, rbx; unsigned __int16 **
0x18005fc9b  call    ?GetPhoneUID@@YAJPEAPEAG@Z; GetPhoneUID(ushort * *)
0x18005fca0  test    eax, eax
0x18005fca2  jns     loc_18005FDB6
0x18005fca8  mov     rcx, rbx
0x18005fcab  call    GetClientMDMID
0x18005fcb0  test    eax, eax
0x18005fcb2  jns     loc_18005FDB6
0x18005fcb8  xorps   xmm0, xmm0
0x18005fcbb  lea     rcx, [rsp+48h+pguid]; pguid
0x18005fcc0  movups  xmmword ptr [rsp+48h+pguid.Data1], xmm0
0x18005fcc5  call    cs:__imp_CoCreateGuid
0x18005fccc  nop     dword ptr [rax+rax+00h]
0x18005fcd1  test    eax, eax
0x18005fcd3  js      loc_18005FDB6
0x18005fcd9  mov     edx, 44h ; 'D'; uBytes
0x18005fcde  xor     ecx, ecx; uFlags
0x18005fce0  call    cs:__imp_LocalAlloc
0x18005fce7  nop     dword ptr [rax+rax+00h]
0x18005fcec  mov     [rbx], rax
0x18005fcef  mov     r9, rax
0x18005fcf2  test    rax, rax
0x18005fcf5  jnz     short loc_18005FD01
0x18005fcf7  mov     eax, 8007000Eh
0x18005fcfc  jmp     loc_18005FDB6
0x18005fd01  lea     rdx, [rsp+48h+var_28]; unsigned int *
0x18005fd06  mov     [rsp+48h+var_28], 0
0x18005fd0e  mov     ecx, 20h ; ' '; unsigned __int64
0x18005fd13  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18005fd18  test    eax, eax
0x18005fd1a  js      loc_18005FDB6
0x18005fd20  mov     eax, [rsp+48h+var_28]
0x18005fd24  lea     ecx, [rax+1]
0x18005fd27  cmp     ecx, eax
0x18005fd29  jnb     short loc_18005FD35
0x18005fd2b  mov     eax, 80070216h
0x18005fd30  jmp     loc_18005FDB6
0x18005fd35  cmp     ecx, 22h ; '"'
0x18005fd38  ja      loc_18005FC7D
0x18005fd3e  mov     edx, 1
0x18005fd43  lea     r10, a0123456789abcd_0; "0123456789ABCDEF"
0x18005fd4a  lea     eax, [rdx-1]
0x18005fd4d  mov     r8d, edx
0x18005fd50  mov     ecx, eax
0x18005fd52  inc     edx
0x18005fd54  movzx   eax, byte ptr [rsp+rax+48h+pguid.Data1]
0x18005fd59  shr     rax, 4
0x18005fd5d  movzx   eax, word ptr [r10+rax*2]
0x18005fd62  mov     [r9], ax
0x18005fd66  lea     r9, [r9+4]
0x18005fd6a  movzx   eax, byte ptr [rsp+rcx+48h+pguid.Data1]
0x18005fd6f  and     eax, 0Fh
0x18005fd72  movzx   eax, word ptr [r10+rax*2]
0x18005fd77  mov     [r9-2], ax
0x18005fd7c  cmp     edx, 10h
0x18005fd7f  jnz     short loc_18005FD4A
0x18005fd81  movzx   eax, byte ptr [rsp+r8+48h+pguid.Data1]
0x18005fd87  shr     rax, 4
0x18005fd8b  movzx   eax, word ptr [r10+rax*2]
0x18005fd90  mov     [r9], ax
0x18005fd94  movzx   eax, byte ptr [rsp+r8+48h+pguid.Data1]
0x18005fd9a  and     eax, 0Fh
0x18005fd9d  movzx   eax, word ptr [r10+rax*2]
0x18005fda2  mov     [r9+2], ax
0x18005fda7  xor     eax, eax
0x18005fda9  mov     [r9+4], ax
0x18005fdae  mov     rcx, [rbx]; unsigned __int16 *
0x18005fdb1  call    ?DMSetDeviceClientID@@YAJPEBG@Z; DMSetDeviceClientID(ushort const *)
0x18005fdb6  mov     rcx, [rsp+48h+var_10]
0x18005fdbb  xor     rcx, rsp; StackCookie
0x18005fdbe  call    __security_check_cookie
0x18005fdc3  add     rsp, 40h
0x18005fdc7  pop     rbx
0x18005fdc8  retn
```
