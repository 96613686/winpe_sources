# MaxSecurityManager::ProcessUrlActionEx(ushort const *,ulong,uchar *,ulong,uchar *,ulong,ulong,ulong,ulong *)

- ea: `0x180009a60`
- end: `0x180009ad4`
- name: `?ProcessUrlActionEx@MaxSecurityManager@@UEAAJPEBGKPEAEK1KKKPEAK@Z`
- size: `116`
- prototype: `__int64 __fastcall(MaxSecurityManager *this, const unsigned __int16 *, int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009a60`

## pseudocode

```c
__int64 __fastcall MaxSecurityManager::ProcessUrlActionEx(
        MaxSecurityManager *this,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int *a10)
{
  if ( a10 && a4 )
  {
    switch ( a3 )
    {
      case 6656:
        if ( a5 >= 4 )
        {
          *(_DWORD *)a4 = 196608;
          goto LABEL_14;
        }
        break;
      case 7168:
        if ( a5 )
        {
          *a4 = 0;
          goto LABEL_14;
        }
        break;
      case 7685:
        if ( a5 >= 4 )
        {
          *(_DWORD *)a4 = 0x10000;
          goto LABEL_14;
        }
        break;
      default:
        if ( a5 )
        {
          *a4 = 3;
LABEL_14:
          *a10 = 0;
          return 1;
        }
        break;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180009a60  mov     rax, [rsp+arg_48]
0x180009a65  test    rax, rax
0x180009a68  jz      short loc_180009ACE
0x180009a6a  test    r9, r9
0x180009a6d  jz      short loc_180009ACE
0x180009a6f  cmp     r8d, 1A00h
0x180009a76  jz      short loc_180009AB4
0x180009a78  cmp     r8d, 1C00h
0x180009a7f  jz      short loc_180009AA7
0x180009a81  cmp     r8d, 1E05h
0x180009a88  jz      short loc_180009A97
0x180009a8a  cmp     [rsp+arg_20], 1
0x180009a8f  jb      short loc_180009ACE
0x180009a91  mov     byte ptr [r9], 3
0x180009a95  jmp     short loc_180009AC2
0x180009a97  cmp     [rsp+arg_20], 4
0x180009a9c  jb      short loc_180009ACE
0x180009a9e  mov     dword ptr [r9], 10000h
0x180009aa5  jmp     short loc_180009AC2
0x180009aa7  cmp     [rsp+arg_20], 1
0x180009aac  jb      short loc_180009ACE
0x180009aae  mov     byte ptr [r9], 0
0x180009ab2  jmp     short loc_180009AC2
0x180009ab4  cmp     [rsp+arg_20], 4
0x180009ab9  jb      short loc_180009ACE
0x180009abb  mov     dword ptr [r9], 30000h
0x180009ac2  mov     dword ptr [rax], 0
0x180009ac8  mov     eax, 1
0x180009acd  retn
0x180009ace  mov     eax, 80070057h
0x180009ad3  retn
```
