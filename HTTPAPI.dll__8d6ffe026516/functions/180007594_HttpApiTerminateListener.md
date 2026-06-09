# HttpApiTerminateListener

- ea: `0x180007594`
- end: `0x18000762a`
- name: `HttpApiTerminateListener`
- size: `150`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800034a0`
- `0x180003ad0`

## callees

- `0x180007594`
- `0x18000bdd0`
- `0x18000be2c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075ea`

## pseudocode

```c
__int64 __fastcall HttpApiTerminateListener(HANDLE a1, __int64 a2, __int64 a3)
{
  char v3; // di
  unsigned int v4; // ebx

  v3 = (char)a1;
  v4 = 87;
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_L((__int64)a1, 0x1Au, (ULONGLONG)WPP_d1f5b049c58935796a293ebb03e09278_Traceguids, (int)a1);
  if ( (v3 & 1) != 0 )
  {
    if ( dword_180012768 )
    {
      v4 = 0;
      if ( dword_180012768 == 1 )
      {
        a1 = g_CommunicationChannel;
        if ( g_CommunicationChannel )
        {
          CloseHandle(g_CommunicationChannel);
          g_CommunicationChannel = 0;
        }
        dword_180012768 = 0;
      }
      else
      {
        --dword_180012768;
      }
    }
    else
    {
      v4 = 1114;
    }
  }
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_Dd((__int64)a1, 0x1Bu, a3, v4);
  return v4;
}

```

## disassembly

```asm
0x180007594  mov     [rsp+arg_0], rbx
0x180007599  push    rdi
0x18000759a  sub     rsp, 30h
0x18000759e  mov     edi, ecx
0x1800075a0  mov     ebx, 57h ; 'W'
0x1800075a5  test    cs:byte_1800126A3, 4
0x1800075ac  jz      short loc_1800075C0
0x1800075ae  lea     edx, [rbx-3Dh]
0x1800075b1  mov     r9d, ecx
0x1800075b4  lea     r8, WPP_d1f5b049c58935796a293ebb03e09278_Traceguids
0x1800075bb  call    WPP_SF_L
0x1800075c0  test    dil, 1
0x1800075c4  jz      short loc_180007607
0x1800075c6  mov     eax, cs:dword_180012768
0x1800075cc  test    eax, eax
0x1800075ce  jnz     short loc_1800075D7
0x1800075d0  mov     ebx, 45Ah
0x1800075d5  jmp     short loc_180007607
0x1800075d7  xor     ebx, ebx
0x1800075d9  cmp     eax, 1
0x1800075dc  jnz     short loc_1800075FF
0x1800075de  mov     rcx, cs:g_CommunicationChannel; hObject
0x1800075e5  test    rcx, rcx
0x1800075e8  jz      short loc_1800075F7
0x1800075ea  call    cs:__imp_CloseHandle
0x1800075f0  mov     cs:g_CommunicationChannel, rbx
0x1800075f7  mov     cs:dword_180012768, ebx
0x1800075fd  jmp     short loc_180007607
0x1800075ff  dec     eax
0x180007601  mov     cs:dword_180012768, eax
0x180007607  test    cs:byte_1800126A3, 4
0x18000760e  jz      short loc_18000761D
0x180007610  mov     edx, 1Bh
0x180007615  mov     r9d, ebx
0x180007618  call    WPP_SF_Dd
0x18000761d  mov     eax, ebx
0x18000761f  mov     rbx, [rsp+38h+arg_0]
0x180007624  add     rsp, 30h
0x180007628  pop     rdi
0x180007629  retn
```
