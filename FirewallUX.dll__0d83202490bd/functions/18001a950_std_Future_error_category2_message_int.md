# std::_Future_error_category2::message(int)

- ea: `0x18001a950`
- end: `0x18001a9b1`
- name: `?message@_Future_error_category2@std@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@H@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180015cfc`
- `0x18001a950`

## import_xrefs

- `msvcp_win!?_Syserror_map@std@@YAPEBDH@Z` at `0x18001a973`
- `msvcp_win!?_Syserror_map@std@@YAPEBDH@Z` at `0x18001a973`

## string_xrefs

- `0x18001a990`: `future already retrieved`
- `0x18001a987`: `promise already satisfied`

## pseudocode

```c
__int64 __fastcall std::_Future_error_category2::message(__int64 a1, __int64 a2, int a3)
{
  const char *v4; // rdx

  switch ( a3 )
  {
    case 1:
      v4 = "broken promise";
      break;
    case 2:
      v4 = "future already retrieved";
      break;
    case 3:
      v4 = "promise already satisfied";
      break;
    case 4:
      v4 = "no state";
      break;
    default:
      v4 = std::_Syserror_map(a3);
      break;
  }
  std::string::string(a2, v4);
  return a2;
}

```

## disassembly

```asm
0x18001a950  push    rbx
0x18001a952  sub     rsp, 30h
0x18001a956  mov     ecx, r8d
0x18001a959  mov     rbx, rdx
0x18001a95c  sub     ecx, 1
0x18001a95f  jz      short loc_18001A999
0x18001a961  sub     ecx, 1
0x18001a964  jz      short loc_18001A990
0x18001a966  sub     ecx, 1
0x18001a969  jz      short loc_18001A987
0x18001a96b  cmp     ecx, 1
0x18001a96e  jz      short loc_18001A97E
0x18001a970  mov     ecx, r8d
0x18001a973  call    cs:__imp_?_Syserror_map@std@@YAPEBDH@Z; std::_Syserror_map(int)
0x18001a979  mov     rdx, rax
0x18001a97c  jmp     short loc_18001A9A0
0x18001a97e  lea     rdx, aNoState; "no state"
0x18001a985  jmp     short loc_18001A9A0
0x18001a987  lea     rdx, aPromiseAlready; "promise already satisfied"
0x18001a98e  jmp     short loc_18001A9A0
0x18001a990  lea     rdx, aFutureAlreadyR; "future already retrieved"
0x18001a997  jmp     short loc_18001A9A0
0x18001a999  lea     rdx, aBrokenPromise; "broken promise"
0x18001a9a0  mov     rcx, rbx
0x18001a9a3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001a9a8  mov     rax, rbx
0x18001a9ab  add     rsp, 30h
0x18001a9af  pop     rbx
0x18001a9b0  retn
```
