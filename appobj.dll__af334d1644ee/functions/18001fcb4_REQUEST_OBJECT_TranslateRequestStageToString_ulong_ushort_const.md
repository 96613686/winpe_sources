# REQUEST_OBJECT::TranslateRequestStageToString(ulong,ushort const * *)

- ea: `0x18001fcb4`
- end: `0x18001fe02`
- name: `?TranslateRequestStageToString@REQUEST_OBJECT@@AEAAJKPEAPEBG@Z`
- size: `334`
- prototype: `__int64 __fastcall(REQUEST_OBJECT *__hidden this, unsigned int, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x18001ed98`

## callees

- `0x18001fcb4`

## string_xrefs

- `0x18001fd25`: `ResolveRequestCache`
- `0x18001fdea`: `UpdateRequestCache`
- `0x18001fdbd`: `ReadEntity`
- `0x18001fdad`: `MapPath`

## pseudocode

```c
__int64 __fastcall REQUEST_OBJECT::TranslateRequestStageToString(
        REQUEST_OBJECT *this,
        unsigned int a2,
        const unsigned __int16 **a3)
{
  unsigned int v3; // ecx
  unsigned int v4; // edx
  unsigned int v5; // edx
  unsigned int v6; // edx
  unsigned int v7; // edx
  unsigned int v8; // edx
  unsigned int v9; // edx
  const unsigned __int16 *v10; // rax

  if ( a3 )
  {
    if ( a2 > 0x80 )
    {
      switch ( a2 )
      {
        case 0x100u:
          v10 = L"ReleaseRequestState";
          goto LABEL_39;
        case 0x200u:
          v10 = L"UpdateRequestCache";
          goto LABEL_39;
        case 0x400u:
          v10 = L"LogRequest";
          goto LABEL_39;
        case 0x800u:
          v10 = L"EndRequest";
          goto LABEL_39;
        case 0x10000000u:
          v10 = L"CustomNotification";
          goto LABEL_39;
        case 0x20000000u:
          v10 = L"SendResponse";
          goto LABEL_39;
        case 0x40000000u:
          v10 = L"ReadEntity";
          goto LABEL_39;
        case 0x80000000:
          v10 = L"MapPath";
          goto LABEL_39;
      }
    }
    else
    {
      if ( a2 == 128 )
      {
        v10 = L"ExecuteRequestHandler";
        goto LABEL_39;
      }
      if ( !a2 )
      {
        v10 = L"PreBeginRequest";
        goto LABEL_39;
      }
      v4 = a2 - 1;
      if ( !v4 )
      {
        v10 = L"BeginRequest";
        goto LABEL_39;
      }
      v5 = v4 - 1;
      if ( !v5 )
      {
        v10 = L"AuthenticateRequest";
        goto LABEL_39;
      }
      v6 = v5 - 2;
      if ( !v6 )
      {
        v10 = L"AuthorizeRequest";
        goto LABEL_39;
      }
      v7 = v6 - 4;
      if ( !v7 )
      {
        v10 = L"ResolveRequestCache";
        goto LABEL_39;
      }
      v8 = v7 - 8;
      if ( !v8 )
      {
        v10 = L"MapRequestHandler";
        goto LABEL_39;
      }
      v9 = v8 - 16;
      if ( !v9 )
      {
        v10 = L"AcquireRequestState";
        goto LABEL_39;
      }
      if ( v9 == 32 )
      {
        v10 = L"PreExecuteRequestHandler";
LABEL_39:
        v3 = 0;
        *a3 = v10;
        return v3;
      }
    }
    return (unsigned int)-2147023728;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x18001fcb4  test    r8, r8
0x18001fcb7  jnz     short loc_18001FCC3
0x18001fcb9  mov     ecx, 80070057h
0x18001fcbe  jmp     loc_18001FDFF
0x18001fcc3  mov     eax, 80h
0x18001fcc8  cmp     edx, eax
0x18001fcca  ja      loc_18001FD6D
0x18001fcd0  jz      loc_18001FD61
0x18001fcd6  test    edx, edx
0x18001fcd8  jz      short loc_18001FD55
0x18001fcda  sub     edx, 1
0x18001fcdd  jz      short loc_18001FD49
0x18001fcdf  sub     edx, 1
0x18001fce2  jz      short loc_18001FD3D
0x18001fce4  sub     edx, 2
0x18001fce7  jz      short loc_18001FD31
0x18001fce9  sub     edx, 4
0x18001fcec  jz      short loc_18001FD25
0x18001fcee  sub     edx, 8
0x18001fcf1  jz      short loc_18001FD19
0x18001fcf3  sub     edx, 10h
0x18001fcf6  jz      short loc_18001FD0D
0x18001fcf8  cmp     edx, 20h ; ' '
0x18001fcfb  jnz     loc_18001FDB6
0x18001fd01  lea     rax, aPreexecuterequ; "PreExecuteRequestHandler"
0x18001fd08  jmp     loc_18001FDFA
0x18001fd0d  lea     rax, aAcquirerequest; "AcquireRequestState"
0x18001fd14  jmp     loc_18001FDFA
0x18001fd19  lea     rax, aMaprequesthand; "MapRequestHandler"
0x18001fd20  jmp     loc_18001FDFA
0x18001fd25  lea     rax, aResolverequest; "ResolveRequestCache"
0x18001fd2c  jmp     loc_18001FDFA
0x18001fd31  lea     rax, aAuthorizereque; "AuthorizeRequest"
0x18001fd38  jmp     loc_18001FDFA
0x18001fd3d  lea     rax, aAuthenticatere; "AuthenticateRequest"
0x18001fd44  jmp     loc_18001FDFA
0x18001fd49  lea     rax, aBeginrequest; "BeginRequest"
0x18001fd50  jmp     loc_18001FDFA
0x18001fd55  lea     rax, aPrebeginreques; "PreBeginRequest"
0x18001fd5c  jmp     loc_18001FDFA
0x18001fd61  lea     rax, aExecuterequest; "ExecuteRequestHandler"
0x18001fd68  jmp     loc_18001FDFA
0x18001fd6d  cmp     edx, 100h
0x18001fd73  jz      short loc_18001FDF3
0x18001fd75  cmp     edx, 200h
0x18001fd7b  jz      short loc_18001FDEA
0x18001fd7d  cmp     edx, 400h
0x18001fd83  jz      short loc_18001FDE1
0x18001fd85  cmp     edx, 800h
0x18001fd8b  jz      short loc_18001FDD8
0x18001fd8d  cmp     edx, 10000000h
0x18001fd93  jz      short loc_18001FDCF
0x18001fd95  cmp     edx, 20000000h
0x18001fd9b  jz      short loc_18001FDC6
0x18001fd9d  cmp     edx, 40000000h
0x18001fda3  jz      short loc_18001FDBD
0x18001fda5  cmp     edx, 80000000h
0x18001fdab  jnz     short loc_18001FDB6
0x18001fdad  lea     rax, aMappath; "MapPath"
0x18001fdb4  jmp     short loc_18001FDFA
0x18001fdb6  mov     ecx, 80070490h
0x18001fdbb  jmp     short loc_18001FDFF
0x18001fdbd  lea     rax, aReadentity; "ReadEntity"
0x18001fdc4  jmp     short loc_18001FDFA
0x18001fdc6  lea     rax, aSendresponse; "SendResponse"
0x18001fdcd  jmp     short loc_18001FDFA
0x18001fdcf  lea     rax, aCustomnotifica; "CustomNotification"
0x18001fdd6  jmp     short loc_18001FDFA
0x18001fdd8  lea     rax, aEndrequest; "EndRequest"
0x18001fddf  jmp     short loc_18001FDFA
0x18001fde1  lea     rax, aLogrequest; "LogRequest"
0x18001fde8  jmp     short loc_18001FDFA
0x18001fdea  lea     rax, aUpdaterequestc; "UpdateRequestCache"
0x18001fdf1  jmp     short loc_18001FDFA
0x18001fdf3  lea     rax, aReleaserequest; "ReleaseRequestState"
0x18001fdfa  xor     ecx, ecx
0x18001fdfc  mov     [r8], rax
0x18001fdff  mov     eax, ecx
0x18001fe01  retn
```
