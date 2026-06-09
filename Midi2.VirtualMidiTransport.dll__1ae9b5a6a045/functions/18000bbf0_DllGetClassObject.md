# DllGetClassObject

- ea: `0x18000bbf0`
- end: `0x18000bcf6`
- name: `DllGetClassObject`
- size: `262`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000bbf0`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bc8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bc8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bcb8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bcb8`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v6; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v7; // rcx
  __int64 *v8; // r9
  struct ATL::_ATL_OBJMAP_ENTRY30 *v9; // rsi
  _DWORD *v10; // rdx
  _QWORD *v11; // rdi

  if ( !ATL::_AtlComModule )
    return -2147418113;
  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v6 = 0;
  v7 = off_18002D100;
  v8 = off_18002D108;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_18002D108 )
  {
    v9 = *v7;
    if ( *v7 )
    {
      if ( *((_QWORD *)v9 + 2) )
      {
        v10 = *(_DWORD **)v9;
        if ( rclsid->Data1 == **(_DWORD **)v9
          && *(_DWORD *)&rclsid->Data2 == v10[1]
          && *(_DWORD *)rclsid->Data4 == v10[2]
          && *(_DWORD *)&rclsid->Data4[4] == v10[3] )
        {
          v11 = (_QWORD *)((char *)v9 + 32);
          if ( !*((_QWORD *)v9 + 4) )
          {
            EnterCriticalSection(&stru_18002D110);
            if ( !*v11 )
              v6 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v9 + 2))(
                     *((_QWORD *)v9 + 3),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     (__int64)v9 + 32);
            LeaveCriticalSection(&stru_18002D110);
          }
          if ( *v11 )
            v6 = (**(__int64 (__fastcall ***)(_QWORD, const IID *const, LPVOID *, __int64 *))*v11)(*v11, riid, ppv, v8);
          break;
        }
      }
    }
    ++v7;
  }
  if ( !*ppv && !v6 )
    return -2147221231;
  return v6;
}

```

## disassembly

```asm
0x18000bbf0  push    rbx
0x18000bbf2  push    rbp
0x18000bbf3  push    rsi
0x18000bbf4  push    rdi
0x18000bbf5  push    r14
0x18000bbf7  sub     rsp, 20h
0x18000bbfb  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000bc02  mov     r14, r8
0x18000bc05  mov     r8, rcx
0x18000bc08  mov     rbp, rdx
0x18000bc0b  jnz     short loc_18000BC17
0x18000bc0d  mov     ebx, 8000FFFFh
0x18000bc12  jmp     loc_18000BCE9
0x18000bc17  test    r14, r14
0x18000bc1a  jnz     short loc_18000BC26
0x18000bc1c  mov     ebx, 80004003h
0x18000bc21  jmp     loc_18000BCE9
0x18000bc26  mov     qword ptr [r14], 0
0x18000bc2d  xor     ebx, ebx
0x18000bc2f  mov     rcx, cs:off_18002D100
0x18000bc36  mov     r9, cs:off_18002D108
0x18000bc3d  jmp     short loc_18000BC76
0x18000bc3f  mov     rsi, [rcx]
0x18000bc42  test    rsi, rsi
0x18000bc45  jz      short loc_18000BC72
0x18000bc47  cmp     [rsi+10h], rbx
0x18000bc4b  jz      short loc_18000BC72
0x18000bc4d  mov     rdx, [rsi]
0x18000bc50  mov     eax, [rdx]
0x18000bc52  cmp     [r8], eax
0x18000bc55  jnz     short loc_18000BC72
0x18000bc57  mov     eax, [rdx+4]
0x18000bc5a  cmp     [r8+4], eax
0x18000bc5e  jnz     short loc_18000BC72
0x18000bc60  mov     eax, [rdx+8]
0x18000bc63  cmp     [r8+8], eax
0x18000bc67  jnz     short loc_18000BC72
0x18000bc69  mov     eax, [rdx+0Ch]
0x18000bc6c  cmp     [r8+0Ch], eax
0x18000bc70  jz      short loc_18000BC7D
0x18000bc72  add     rcx, 8
0x18000bc76  cmp     rcx, r9
0x18000bc79  jb      short loc_18000BC3F
0x18000bc7b  jmp     short loc_18000BCD9
0x18000bc7d  lea     rdi, [rsi+20h]
0x18000bc81  cmp     [rdi], rbx
0x18000bc84  jnz     short loc_18000BCBE
0x18000bc86  lea     rcx, stru_18002D110; lpCriticalSection
0x18000bc8d  call    cs:__imp_EnterCriticalSection
0x18000bc93  cmp     [rdi], rbx
0x18000bc96  jnz     short loc_18000BCB1
0x18000bc98  mov     rcx, [rsi+18h]
0x18000bc9c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000bca3  mov     rax, [rsi+10h]
0x18000bca7  mov     r8, rdi
0x18000bcaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcaf  mov     ebx, eax
0x18000bcb1  lea     rcx, stru_18002D110; lpCriticalSection
0x18000bcb8  call    cs:__imp_LeaveCriticalSection
0x18000bcbe  mov     rcx, [rdi]
0x18000bcc1  test    rcx, rcx
0x18000bcc4  jz      short loc_18000BCD9
0x18000bcc6  mov     rax, [rcx]
0x18000bcc9  mov     r8, r14
0x18000bccc  mov     rdx, rbp
0x18000bccf  mov     rax, [rax]
0x18000bcd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcd7  mov     ebx, eax
0x18000bcd9  cmp     qword ptr [r14], 0
0x18000bcdd  jnz     short loc_18000BCE9
0x18000bcdf  test    ebx, ebx
0x18000bce1  mov     eax, 80040111h
0x18000bce6  cmovz   ebx, eax
0x18000bce9  mov     eax, ebx
0x18000bceb  add     rsp, 20h
0x18000bcef  pop     r14
0x18000bcf1  pop     rdi
0x18000bcf2  pop     rsi
0x18000bcf3  pop     rbp
0x18000bcf4  pop     rbx
0x18000bcf5  retn
```
