# DllGetClassObject

- ea: `0x18000ad90`
- end: `0x18000ae96`
- name: `DllGetClassObject`
- size: `262`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000ad90`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ae2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ae2d`

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
  v7 = off_18001B100;
  v8 = off_18001B108;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_18001B108 )
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
            EnterCriticalSection(&CriticalSection);
            if ( !*v11 )
              v6 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v9 + 2))(
                     *((_QWORD *)v9 + 3),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     (__int64)v9 + 32);
            LeaveCriticalSection(&CriticalSection);
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
0x18000ad90  push    rbx
0x18000ad92  push    rbp
0x18000ad93  push    rsi
0x18000ad94  push    rdi
0x18000ad95  push    r14
0x18000ad97  sub     rsp, 20h
0x18000ad9b  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000ada2  mov     r14, r8
0x18000ada5  mov     r8, rcx
0x18000ada8  mov     rbp, rdx
0x18000adab  jnz     short loc_18000ADB7
0x18000adad  mov     ebx, 8000FFFFh
0x18000adb2  jmp     loc_18000AE89
0x18000adb7  test    r14, r14
0x18000adba  jnz     short loc_18000ADC6
0x18000adbc  mov     ebx, 80004003h
0x18000adc1  jmp     loc_18000AE89
0x18000adc6  mov     qword ptr [r14], 0
0x18000adcd  xor     ebx, ebx
0x18000adcf  mov     rcx, cs:off_18001B100
0x18000add6  mov     r9, cs:off_18001B108
0x18000addd  jmp     short loc_18000AE16
0x18000addf  mov     rsi, [rcx]
0x18000ade2  test    rsi, rsi
0x18000ade5  jz      short loc_18000AE12
0x18000ade7  cmp     [rsi+10h], rbx
0x18000adeb  jz      short loc_18000AE12
0x18000aded  mov     rdx, [rsi]
0x18000adf0  mov     eax, [rdx]
0x18000adf2  cmp     [r8], eax
0x18000adf5  jnz     short loc_18000AE12
0x18000adf7  mov     eax, [rdx+4]
0x18000adfa  cmp     [r8+4], eax
0x18000adfe  jnz     short loc_18000AE12
0x18000ae00  mov     eax, [rdx+8]
0x18000ae03  cmp     [r8+8], eax
0x18000ae07  jnz     short loc_18000AE12
0x18000ae09  mov     eax, [rdx+0Ch]
0x18000ae0c  cmp     [r8+0Ch], eax
0x18000ae10  jz      short loc_18000AE1D
0x18000ae12  add     rcx, 8
0x18000ae16  cmp     rcx, r9
0x18000ae19  jb      short loc_18000ADDF
0x18000ae1b  jmp     short loc_18000AE79
0x18000ae1d  lea     rdi, [rsi+20h]
0x18000ae21  cmp     [rdi], rbx
0x18000ae24  jnz     short loc_18000AE5E
0x18000ae26  lea     rcx, CriticalSection; lpCriticalSection
0x18000ae2d  call    cs:__imp_EnterCriticalSection
0x18000ae33  cmp     [rdi], rbx
0x18000ae36  jnz     short loc_18000AE51
0x18000ae38  mov     rcx, [rsi+18h]
0x18000ae3c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000ae43  mov     rax, [rsi+10h]
0x18000ae47  mov     r8, rdi
0x18000ae4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae4f  mov     ebx, eax
0x18000ae51  lea     rcx, CriticalSection; lpCriticalSection
0x18000ae58  call    cs:__imp_LeaveCriticalSection
0x18000ae5e  mov     rcx, [rdi]
0x18000ae61  test    rcx, rcx
0x18000ae64  jz      short loc_18000AE79
0x18000ae66  mov     rax, [rcx]
0x18000ae69  mov     r8, r14
0x18000ae6c  mov     rdx, rbp
0x18000ae6f  mov     rax, [rax]
0x18000ae72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae77  mov     ebx, eax
0x18000ae79  cmp     qword ptr [r14], 0
0x18000ae7d  jnz     short loc_18000AE89
0x18000ae7f  test    ebx, ebx
0x18000ae81  mov     eax, 80040111h
0x18000ae86  cmovz   ebx, eax
0x18000ae89  mov     eax, ebx
0x18000ae8b  add     rsp, 20h
0x18000ae8f  pop     r14
0x18000ae91  pop     rdi
0x18000ae92  pop     rsi
0x18000ae93  pop     rbp
0x18000ae94  pop     rbx
0x18000ae95  retn
```
