# DmGetUserPermissionAsync(ushort const *,ushort const *,DM_IMPORTANCE,ushort const *,ushort const *,int,long (*)(void *,int),void *,void * *,void * *)

- ea: `0x18007a480`
- end: `0x18007a5a3`
- name: `?DmGetUserPermissionAsync@@YAJPEBG0W4DM_IMPORTANCE@@00HP6AJPEAXH@Z2PEAPEAX4@Z`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800520f0`
- `0x18007a480`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a563`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a563`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18007a54f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18007a54f`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMUI_GetUserPermissionAsync` at `0x18007a4b4`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMUI_GetUserPermissionAsync` at `0x18007a4b4`

## pseudocode

```c
__int64 __fastcall DmGetUserPermissionAsync(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9,
        _QWORD *a10)
{
  int UserPermissionAsync; // ebx
  _OWORD *v11; // rax
  HANDLE Thread; // rax
  signed int LastError; // eax

  UserPermissionAsync = DMUI_GetUserPermissionAsync(a1, a2, a3);
  if ( UserPermissionAsync >= 0 )
  {
    v11 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
    if ( v11 )
    {
      UserPermissionAsync = -2147024882;
      *v11 = 0;
      v11[1] = 0;
    }
    else
    {
      MEMORY[0] = a7;
      MEMORY[8] = a8;
      MEMORY[0x18] = 0;
      MEMORY[0x10] = 0;
      Thread = CreateThread(0, 0, ListenOnButtonClick, 0, 0, 0);
      if ( Thread )
      {
        *a10 = Thread;
        *a9 = 0;
      }
      else
      {
        LastError = GetLastError();
        UserPermissionAsync = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  return (unsigned int)UserPermissionAsync;
}

```

## disassembly

```asm
0x18007a480  mov     r11, rsp
0x18007a483  push    rbx
0x18007a484  sub     rsp, 50h
0x18007a488  lea     rax, [r11-18h]
0x18007a48c  mov     qword ptr [r11-18h], 0
0x18007a494  mov     [r11-28h], rax
0x18007a498  lea     rax, [r11-10h]
0x18007a49c  mov     [r11-30h], rax
0x18007a4a0  mov     rax, [rsp+58h+arg_20]
0x18007a4a8  mov     [r11-38h], rax
0x18007a4ac  mov     qword ptr [r11-10h], 0
0x18007a4b4  call    cs:__imp_DMUI_GetUserPermissionAsync
0x18007a4bb  nop     dword ptr [rax+rax+00h]
0x18007a4c0  mov     ebx, eax
0x18007a4c2  test    eax, eax
0x18007a4c4  js      loc_18007A59A
0x18007a4ca  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007a4d1  mov     ecx, 20h ; ' '; unsigned __int64
0x18007a4d6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18007a4db  test    rax, rax
0x18007a4de  jz      short loc_18007A4F4
0x18007a4e0  xorps   xmm0, xmm0
0x18007a4e3  mov     ebx, 8007000Eh
0x18007a4e8  movups  xmmword ptr [rax], xmm0
0x18007a4eb  movups  xmmword ptr [rax+10h], xmm0
0x18007a4ef  jmp     loc_18007A59A
0x18007a4f4  mov     rax, [rsp+58h+arg_30]
0x18007a4fc  lea     r8, ?ListenOnButtonClick@@YAKPEAX@Z; lpStartAddress
0x18007a503  mov     large ds:0, rax
0x18007a50d  xor     r9d, r9d; lpParameter
0x18007a510  mov     rax, [rsp+58h+arg_38]
0x18007a518  xor     edx, edx; dwStackSize
0x18007a51a  mov     ds:8, rax
0x18007a522  xor     ecx, ecx; lpThreadAttributes
0x18007a524  mov     rax, [rsp+58h+var_18]
0x18007a529  mov     ds:18h, rax
0x18007a531  mov     rax, [rsp+58h+var_10]
0x18007a536  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x18007a53f  mov     ds:10h, rax
0x18007a547  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18007a54f  call    cs:__imp_CreateThread
0x18007a556  nop     dword ptr [rax+rax+00h]
0x18007a55b  mov     rcx, rax
0x18007a55e  test    rax, rax
0x18007a561  jnz     short loc_18007A580
0x18007a563  call    cs:__imp_GetLastError
0x18007a56a  nop     dword ptr [rax+rax+00h]
0x18007a56f  mov     ebx, eax
0x18007a571  test    eax, eax
0x18007a573  jle     short loc_18007A59A
0x18007a575  movzx   ebx, ax
0x18007a578  or      ebx, 80070000h
0x18007a57e  jmp     short loc_18007A59A
0x18007a580  mov     rax, [rsp+58h+arg_48]
0x18007a588  mov     [rax], rcx
0x18007a58b  mov     rax, [rsp+58h+arg_40]
0x18007a593  mov     qword ptr [rax], 0
0x18007a59a  mov     eax, ebx
0x18007a59c  add     rsp, 50h
0x18007a5a0  pop     rbx
0x18007a5a1  retn
```
