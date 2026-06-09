# std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>,void *> *>,std::_Tree_node<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>,void *> * const)

- ea: `0x180024974`
- end: `0x180024b9d`
- name: `?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@PEAX@std@@@2@QEAU32@@Z`
- size: `553`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180021190`
- `0x18002138c`
- `0x1800214e4`
- `0x180021644`
- `0x18002179c`
- `0x18002ae94`
- `0x180035870`
- `0x18003652c`

## callees

- `0x180024974`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>>>::_Insert_node(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v4; // r10
  _QWORD *v5; // rax
  __int64 v6; // rax
  _QWORD *i; // rdx
  __int64 v8; // rcx
  __int64 *v9; // r9
  __int64 v10; // rax
  _QWORD *v11; // r9
  _QWORD *v12; // rax
  _QWORD *v13; // rcx
  _QWORD *v14; // r9
  __int64 v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // r9
  __int64 v18; // rax
  _QWORD *v19; // rax
  _QWORD *v20; // rax

  ++a1[1];
  v4 = (_QWORD *)*a1;
  v5 = *(_QWORD **)a2;
  *(_QWORD *)(a3 + 8) = *(_QWORD *)a2;
  if ( v5 != v4 )
  {
    if ( *(_DWORD *)(a2 + 8) )
    {
      *v5 = a3;
      if ( v5 == (_QWORD *)*v4 )
        *v4 = a3;
    }
    else
    {
      v5[2] = a3;
      if ( v5 == (_QWORD *)v4[2] )
        v4[2] = a3;
    }
    v6 = *(_QWORD *)(a3 + 8);
    for ( i = (_QWORD *)a3; ; v6 = i[1] )
    {
      if ( *(_BYTE *)(v6 + 24) )
      {
        *(_BYTE *)(v4[1] + 24LL) = 1;
        return a3;
      }
      v8 = i[1];
      v9 = *(__int64 **)(v8 + 8);
      v10 = *v9;
      if ( v8 == *v9 )
      {
        v10 = v9[2];
        if ( !*(_BYTE *)(v10 + 24) )
          goto LABEL_29;
        v11 = *(_QWORD **)(v8 + 16);
        if ( i == v11 )
        {
          i = (_QWORD *)i[1];
          *(_QWORD *)(v8 + 16) = *v11;
          if ( !*(_BYTE *)(*v11 + 25LL) )
            *(_QWORD *)(*v11 + 8LL) = v8;
          v11[1] = *(_QWORD *)(v8 + 8);
          if ( v8 == *(_QWORD *)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v11;
          }
          else
          {
            v12 = *(_QWORD **)(v8 + 8);
            if ( v8 == *v12 )
              *v12 = v11;
            else
              v12[2] = v11;
          }
          *v11 = v8;
          *(_QWORD *)(v8 + 8) = v11;
        }
        *(_BYTE *)(i[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
        v13 = *(_QWORD **)(i[1] + 8LL);
        v14 = (_QWORD *)*v13;
        *v13 = *(_QWORD *)(*v13 + 16LL);
        v15 = v14[2];
        if ( !*(_BYTE *)(v15 + 25) )
          *(_QWORD *)(v15 + 8) = v13;
        v14[1] = v13[1];
        if ( v13 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v14;
        }
        else
        {
          v16 = (_QWORD *)v13[1];
          if ( v13 == (_QWORD *)v16[2] )
            v16[2] = v14;
          else
            *v16 = v14;
        }
        v14[2] = v13;
      }
      else
      {
        if ( !*(_BYTE *)(v10 + 24) )
        {
LABEL_29:
          *(_BYTE *)(v8 + 24) = 1;
          *(_BYTE *)(v10 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
          i = *(_QWORD **)(i[1] + 8LL);
          continue;
        }
        v17 = *(_QWORD **)v8;
        if ( i == *(_QWORD **)v8 )
        {
          i = (_QWORD *)i[1];
          *(_QWORD *)v8 = v17[2];
          v18 = v17[2];
          if ( !*(_BYTE *)(v18 + 25) )
            *(_QWORD *)(v18 + 8) = v8;
          v17[1] = *(_QWORD *)(v8 + 8);
          if ( v8 == *(_QWORD *)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v17;
          }
          else
          {
            v19 = *(_QWORD **)(v8 + 8);
            if ( v8 == v19[2] )
              v19[2] = v17;
            else
              *v19 = v17;
          }
          v17[2] = v8;
          *(_QWORD *)(v8 + 8) = v17;
        }
        *(_BYTE *)(i[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
        v13 = *(_QWORD **)(i[1] + 8LL);
        v14 = (_QWORD *)v13[2];
        v13[2] = *v14;
        if ( !*(_BYTE *)(*v14 + 25LL) )
          *(_QWORD *)(*v14 + 8LL) = v13;
        v14[1] = v13[1];
        if ( v13 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v14;
        }
        else
        {
          v20 = (_QWORD *)v13[1];
          if ( v13 == (_QWORD *)*v20 )
            *v20 = v14;
          else
            v20[2] = v14;
        }
        *v14 = v13;
      }
      v13[1] = v14;
    }
  }
  *v4 = a3;
  v4[1] = a3;
  v4[2] = a3;
  *(_BYTE *)(a3 + 24) = 1;
  return a3;
}

```

## disassembly

```asm
0x180024974  mov     [rsp+arg_0], rbx
0x180024979  inc     qword ptr [rcx+8]
0x18002497d  mov     r11, rcx
0x180024980  mov     r10, [rcx]
0x180024983  mov     rax, [rdx]
0x180024986  mov     [r8+8], rax
0x18002498a  cmp     rax, r10
0x18002498d  jnz     short loc_1800249A4
0x18002498f  mov     [r10], r8
0x180024992  mov     [r10+8], r8
0x180024996  mov     [r10+10h], r8
0x18002499a  mov     byte ptr [r8+18h], 1
0x18002499f  jmp     loc_180024B94
0x1800249a4  xor     ebx, ebx
0x1800249a6  cmp     [rdx+8], ebx
0x1800249a9  jnz     short loc_1800249BB
0x1800249ab  mov     [rax+10h], r8
0x1800249af  cmp     rax, [r10+10h]
0x1800249b3  jnz     short loc_1800249C6
0x1800249b5  mov     [r10+10h], r8
0x1800249b9  jmp     short loc_1800249C6
0x1800249bb  mov     [rax], r8
0x1800249be  cmp     rax, [r10]
0x1800249c1  jnz     short loc_1800249C6
0x1800249c3  mov     [r10], r8
0x1800249c6  mov     rax, [r8+8]
0x1800249ca  mov     rdx, r8
0x1800249cd  jmp     loc_180024B83
0x1800249d2  mov     rcx, [rdx+8]
0x1800249d6  mov     r9, [rcx+8]
0x1800249da  mov     rax, [r9]
0x1800249dd  cmp     rcx, rax
0x1800249e0  jnz     loc_180024AA7
0x1800249e6  mov     rax, [r9+10h]
0x1800249ea  cmp     [rax+18h], bl
0x1800249ed  jz      loc_180024AAC
0x1800249f3  mov     r9, [rcx+10h]
0x1800249f7  cmp     rdx, r9
0x1800249fa  jnz     short loc_180024A42
0x1800249fc  mov     rax, [r9]
0x1800249ff  mov     rdx, rcx
0x180024a02  mov     [rcx+10h], rax
0x180024a06  mov     rax, [r9]
0x180024a09  cmp     [rax+19h], bl
0x180024a0c  jnz     short loc_180024A12
0x180024a0e  mov     [rax+8], rcx
0x180024a12  mov     rax, [rcx+8]
0x180024a16  mov     [r9+8], rax
0x180024a1a  mov     rax, [r11]
0x180024a1d  cmp     rcx, [rax+8]
0x180024a21  jnz     short loc_180024A29
0x180024a23  mov     [rax+8], r9
0x180024a27  jmp     short loc_180024A3B
0x180024a29  mov     rax, [rcx+8]
0x180024a2d  cmp     rcx, [rax]
0x180024a30  jnz     short loc_180024A37
0x180024a32  mov     [rax], r9
0x180024a35  jmp     short loc_180024A3B
0x180024a37  mov     [rax+10h], r9
0x180024a3b  mov     [r9], rcx
0x180024a3e  mov     [rcx+8], r9
0x180024a42  mov     rax, [rdx+8]
0x180024a46  mov     byte ptr [rax+18h], 1
0x180024a4a  mov     rax, [rdx+8]
0x180024a4e  mov     rcx, [rax+8]
0x180024a52  mov     [rcx+18h], bl
0x180024a55  mov     rax, [rdx+8]
0x180024a59  mov     rcx, [rax+8]
0x180024a5d  mov     r9, [rcx]
0x180024a60  mov     rax, [r9+10h]
0x180024a64  mov     [rcx], rax
0x180024a67  mov     rax, [r9+10h]
0x180024a6b  cmp     [rax+19h], bl
0x180024a6e  jnz     short loc_180024A74
0x180024a70  mov     [rax+8], rcx
0x180024a74  mov     rax, [rcx+8]
0x180024a78  mov     [r9+8], rax
0x180024a7c  mov     rax, [r11]
0x180024a7f  cmp     rcx, [rax+8]
0x180024a83  jnz     short loc_180024A8B
0x180024a85  mov     [rax+8], r9
0x180024a89  jmp     short loc_180024A9E
0x180024a8b  mov     rax, [rcx+8]
0x180024a8f  cmp     rcx, [rax+10h]
0x180024a93  jnz     short loc_180024A9B
0x180024a95  mov     [rax+10h], r9
0x180024a99  jmp     short loc_180024A9E
0x180024a9b  mov     [rax], r9
0x180024a9e  mov     [r9+10h], rcx
0x180024aa2  jmp     loc_180024B7B
0x180024aa7  cmp     [rax+18h], bl
0x180024aaa  jnz     short loc_180024ACC
0x180024aac  mov     byte ptr [rcx+18h], 1
0x180024ab0  mov     byte ptr [rax+18h], 1
0x180024ab4  mov     rax, [rdx+8]
0x180024ab8  mov     rcx, [rax+8]
0x180024abc  mov     [rcx+18h], bl
0x180024abf  mov     rax, [rdx+8]
0x180024ac3  mov     rdx, [rax+8]
0x180024ac7  jmp     loc_180024B7F
0x180024acc  mov     r9, [rcx]
0x180024acf  cmp     rdx, r9
0x180024ad2  jnz     short loc_180024B1D
0x180024ad4  mov     rax, [r9+10h]
0x180024ad8  mov     rdx, rcx
0x180024adb  mov     [rcx], rax
0x180024ade  mov     rax, [r9+10h]
0x180024ae2  cmp     [rax+19h], bl
0x180024ae5  jnz     short loc_180024AEB
0x180024ae7  mov     [rax+8], rcx
0x180024aeb  mov     rax, [rcx+8]
0x180024aef  mov     [r9+8], rax
0x180024af3  mov     rax, [r11]
0x180024af6  cmp     rcx, [rax+8]
0x180024afa  jnz     short loc_180024B02
0x180024afc  mov     [rax+8], r9
0x180024b00  jmp     short loc_180024B15
0x180024b02  mov     rax, [rcx+8]
0x180024b06  cmp     rcx, [rax+10h]
0x180024b0a  jnz     short loc_180024B12
0x180024b0c  mov     [rax+10h], r9
0x180024b10  jmp     short loc_180024B15
0x180024b12  mov     [rax], r9
0x180024b15  mov     [r9+10h], rcx
0x180024b19  mov     [rcx+8], r9
0x180024b1d  mov     rax, [rdx+8]
0x180024b21  mov     byte ptr [rax+18h], 1
0x180024b25  mov     rax, [rdx+8]
0x180024b29  mov     rcx, [rax+8]
0x180024b2d  mov     [rcx+18h], bl
0x180024b30  mov     rax, [rdx+8]
0x180024b34  mov     rcx, [rax+8]
0x180024b38  mov     r9, [rcx+10h]
0x180024b3c  mov     rax, [r9]
0x180024b3f  mov     [rcx+10h], rax
0x180024b43  mov     rax, [r9]
0x180024b46  cmp     [rax+19h], bl
0x180024b49  jnz     short loc_180024B4F
0x180024b4b  mov     [rax+8], rcx
0x180024b4f  mov     rax, [rcx+8]
0x180024b53  mov     [r9+8], rax
0x180024b57  mov     rax, [r11]
0x180024b5a  cmp     rcx, [rax+8]
0x180024b5e  jnz     short loc_180024B66
0x180024b60  mov     [rax+8], r9
0x180024b64  jmp     short loc_180024B78
0x180024b66  mov     rax, [rcx+8]
0x180024b6a  cmp     rcx, [rax]
0x180024b6d  jnz     short loc_180024B74
0x180024b6f  mov     [rax], r9
0x180024b72  jmp     short loc_180024B78
0x180024b74  mov     [rax+10h], r9
0x180024b78  mov     [r9], rcx
0x180024b7b  mov     [rcx+8], r9
0x180024b7f  mov     rax, [rdx+8]
0x180024b83  cmp     [rax+18h], bl
0x180024b86  jz      loc_1800249D2
0x180024b8c  mov     rax, [r10+8]
0x180024b90  mov     byte ptr [rax+18h], 1
0x180024b94  mov     rbx, [rsp+arg_0]
0x180024b99  mov     rax, r8
0x180024b9c  retn
```
