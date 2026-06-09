# DpspGetDMDispatchInstanceList

- ea: `0x180002f10`
- end: `0x18000301a`
- name: `DpspGetDMDispatchInstanceList`
- size: `266`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800035d0`
- `0x180004864`
- `0x180004b18`
- `0x180004c18`
- `0x180004de4`
- `0x18000c6bc`
- `0x180011fd4`

## callees

- `0x180002f10`
- `0x180009090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002f78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002f32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002f32`

## pseudocode

```c
void __fastcall DpspGetDMDispatchInstanceList(__int64 a1, __int64 a2)
{
  __int64 *v4; // rax
  __int64 *v5; // rcx
  __int64 **v6; // rdx
  __int64 **v7; // rdx

  if ( a1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
    if ( a2 )
    {
      v4 = *(__int64 **)(a1 + 112);
      if ( v4 != (__int64 *)(a1 + 112) )
      {
        do
        {
          if ( *(_DWORD *)(a1 + 28) >= (unsigned int)(*(_DWORD *)(a1 + 32) - *(_DWORD *)(a1 + 44)) )
            break;
          --*(_DWORD *)(a1 + 36);
          v5 = (__int64 *)*v4;
          if ( *(__int64 **)(*v4 + 8) == v4 )
          {
            v6 = (__int64 **)v4[1];
            if ( *v6 == v4 )
            {
              *v6 = v5;
              v5[1] = (__int64)v6;
              _InterlockedOr((volatile signed __int32 *)v4 + 26, 0x10u);
              ++*(_DWORD *)(a1 + 44);
              v7 = *(__int64 ***)(a2 + 8);
              if ( *v7 == (__int64 *)a2 )
                continue;
            }
          }
          __fastfail(3u);
          *v4 = a2;
          v4[1] = (__int64)v7;
          *v7 = v4;
          *(_QWORD *)(a2 + 8) = v4;
          v4 = v5;
        }
        while ( v5 != (__int64 *)(a1 + 112) );
      }
    }
    else
    {
      WdipTraceError(
        (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
        (__int64)L"DpspGetDMDispatchInstanceList",
        1513,
        (const wchar_t *)L"Error = %d",
        87);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  }
  else
  {
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (__int64)L"DpspGetDMDispatchInstanceList",
      1511,
      (const wchar_t *)L"Error = %d",
      87);
  }
}

```

## disassembly

```asm
0x180002f10  mov     [rsp+arg_8], rbx
0x180002f15  push    rsi
0x180002f16  sub     rsp, 30h
0x180002f1a  mov     rsi, rdx
0x180002f1d  mov     rbx, rcx
0x180002f20  test    rcx, rcx
0x180002f23  jz      loc_180002FE7
0x180002f29  add     rcx, 40h ; '@'; lpCriticalSection
0x180002f2d  mov     [rsp+38h+arg_0], rdi
0x180002f32  call    cs:__imp_EnterCriticalSection
0x180002f38  test    rsi, rsi
0x180002f3b  jnz     short loc_180002F7F
0x180002f3d  lea     r9, aErrorD; "Error = %d"
0x180002f44  mov     dword ptr [rsp+38h+Args], 57h ; 'W'; Args
0x180002f4c  mov     r8d, 5E9h; int
0x180002f52  lea     rdx, aDpspgetdmdispa; "DpspGetDMDispatchInstanceList"
0x180002f59  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180002f60  call    WdipTraceError
0x180002f65  lea     rcx, [rbx+40h]
0x180002f69  mov     rdi, [rsp+38h+arg_0]
0x180002f6e  mov     rbx, [rsp+38h+arg_8]
0x180002f73  add     rsp, 30h
0x180002f77  pop     rsi
0x180002f78  jmp     cs:__imp_LeaveCriticalSection
0x180002f7f  mov     rax, [rbx+70h]
0x180002f83  lea     r8, [rbx+70h]
0x180002f87  cmp     rax, r8
0x180002f8a  jz      short loc_180002F65
0x180002f8c  nop     dword ptr [rax+00h]
0x180002f90  mov     ecx, [rbx+20h]
0x180002f93  sub     ecx, [rbx+2Ch]
0x180002f96  cmp     [rbx+1Ch], ecx
0x180002f99  jnb     short loc_180002F65
0x180002f9b  dec     dword ptr [rbx+24h]
0x180002f9e  mov     rcx, [rax]
0x180002fa1  cmp     [rcx+8], rax
0x180002fa5  jnz     short loc_180002FE0
0x180002fa7  mov     rdx, [rax+8]
0x180002fab  cmp     [rdx], rax
0x180002fae  jnz     short loc_180002FE0
0x180002fb0  mov     [rdx], rcx
0x180002fb3  mov     [rcx+8], rdx
0x180002fb7  lock or dword ptr [rax+68h], 10h
0x180002fbc  inc     dword ptr [rbx+2Ch]
0x180002fbf  mov     rdx, [rsi+8]
0x180002fc3  cmp     [rdx], rsi
0x180002fc6  jnz     short loc_180002FE0
0x180002fc8  mov     [rax], rsi
0x180002fcb  mov     [rax+8], rdx
0x180002fcf  mov     [rdx], rax
0x180002fd2  mov     [rsi+8], rax
0x180002fd6  mov     rax, rcx
0x180002fd9  cmp     rcx, r8
0x180002fdc  jnz     short loc_180002F90
0x180002fde  jmp     short loc_180002F65
0x180002fe0  mov     ecx, 3
0x180002fe5  int     29h; Win8: RtlFailFast(ecx)
0x180002fe7  lea     r9, aErrorD; "Error = %d"
0x180002fee  mov     dword ptr [rsp+38h+Args], 57h ; 'W'; Args
0x180002ff6  mov     r8d, 5E7h; int
0x180002ffc  lea     rdx, aDpspgetdmdispa; "DpspGetDMDispatchInstanceList"
0x180003003  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000300a  call    WdipTraceError
0x18000300f  mov     rbx, [rsp+38h+arg_8]
0x180003014  add     rsp, 30h
0x180003018  pop     rsi
0x180003019  retn
```
