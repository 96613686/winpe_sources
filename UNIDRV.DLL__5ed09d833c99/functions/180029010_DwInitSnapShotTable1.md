# DwInitSnapShotTable1

- ea: `0x180029010`
- end: `0x18002c122`
- name: `DwInitSnapShotTable1`
- size: `12562`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800278e0`

## callees

- `0x180029010`
- `0x18002c128`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180029020`
- `KERNEL32!LocalAlloc` at `0x180029020`

## string_xrefs

- `0x180029f00`: `*CyanInMagentaDye`
- `0x180029e7d`: `*MagentaInCyanDye`
- `0x180029a0b`: `*UseSpaceForXMove?`
- `0x18002afbc`: `*UseBMPFontCompression?`
- `0x18002b031`: `*UseMode5Compression?`
- `0x180029c4b`: `*XMoveUnit`
- `0x180029252`: `*ResourceDLL`
- `0x1800298ac`: `*BadCursorMoveInGrxMode`
- `0x18002a05f`: `*MagentaInYellowDye`
- `0x180029f75`: `*YellowInMagentaDye`
- `0x180029b67`: `*XMoveThreshold`
- `0x180029921`: `*YMoveAttributes`
- `0x180029c1a`: `*YMoveThreshold`
- `0x180029d32`: `*LineSpacingMoveUnit`
- `0x18002b538`: `*PrintSchemaPrivateNamespaceURI`
- `0x18002a5cc`: `*MoveToX0BeforeSetColor?`
- `0x180029cbd`: `*YMoveUnit`
- `0x180029a80`: `*AbsXMovesRightOnly?`

## pseudocode

```c
__int64 __fastcall DwInitSnapShotTable1(__int64 a1)
{
  __int64 result; // rax

  result = (__int64)LocalAlloc(0, 0x1C20u);
  *(_QWORD *)(a1 + 176) = result;
  if ( result )
  {
    *(_QWORD *)result = "*GPDSpecVersion";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 16LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 20LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 12LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 8LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 24LL) = 9;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 28LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 32LL) = "*GPDFileVersion";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 48LL) = 16;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 52LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 44LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 40LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 56LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 60LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 64LL) = "*GPDFileName";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 80LL) = 20;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 84LL) = 32;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 76LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 72LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 88LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 92LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 96LL) = "*MasterUnits";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 112LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 116LL) = 16;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 108LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 104LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 120LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 124LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 128LL) = "*ModelName";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 144LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 148LL) = 24;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 140LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 136LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 152LL) = 9;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 156LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 160LL) = "*PrinterType";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 176LL) = 68;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 180LL) = 40;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 172LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 168LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 184LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 188LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 192LL) = "*ResourceDLL";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 208LL) = 80;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 212LL) = 56;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 204LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 200LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 216LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 220LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 224LL) = "*MaxCopies";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 240LL) = 88;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 244LL) = 64;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 236LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 232LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 248LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 252LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 256LL) = "*DefaultCopies";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 272LL) = 92;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 276LL) = 68;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 268LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 264LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 280LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 284LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 288LL) = "*FontCartSlots";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 304LL) = 96;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 308LL) = 72;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 300LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 296LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 312LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 316LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 320LL) = "*OEMCustomData";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 336LL) = 24;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 340LL) = 80;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 332LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 328LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 344LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 348LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 352LL) = "*OEMCustomData";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 368LL) = 24;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 372LL) = 88;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 364LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 360LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 376LL) = 4096;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 380LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 384LL) = "*RotateCoordinate?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 400LL) = 116;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 404LL) = 92;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 396LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 392LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 408LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 412LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 416LL) = "*RotateRaster?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 432LL) = 124;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 436LL) = 96;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 428LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 424LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 440LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 444LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 448LL) = "*TextCaps";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 464LL) = 128;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 468LL) = 100;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 460LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 456LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 472LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 476LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 480LL) = "*RotateFont?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 496LL) = 132;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 500LL) = 104;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 492LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 488LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 504LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 508LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 512LL) = "*MemoryUsage";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 528LL) = 136;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 532LL) = 108;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 524LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 520LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 536LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 540LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 544LL) = "*ReselectFont";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 560LL) = 140;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 564LL) = 112;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 556LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 552LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 568LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 572LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 576LL) = "*OEMPrintingCallbacks";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 592LL) = 172;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 596LL) = 116;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 588LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 584LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 600LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 604LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 608LL) = "*CursorXAfterCR";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 624LL) = 176;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 628LL) = 120;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 620LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 616LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 632LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 636LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 640LL) = "*BadCursorMoveInGrxMode";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 656LL) = 180;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 660LL) = 124;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 652LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 648LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 664LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 668LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 672LL) = "*YMoveAttributes";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 688LL) = 196;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 692LL) = 128;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 684LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 680LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 696LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 700LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 704LL) = "*MaxLineSpacing";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 720LL) = 200;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 724LL) = 132;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 716LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 712LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 728LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 732LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 736LL) = "*UseSpaceForXMove?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 752LL) = 204;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 756LL) = 140;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 748LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 744LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 760LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 764LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 768LL) = "*AbsXMovesRightOnly?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 784LL) = 208;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 788LL) = 144;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 780LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 776LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 792LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 796LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 800LL) = "*EjectPageWithFF?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 816LL) = 188;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 820LL) = 136;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 812LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 808LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 824LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 828LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 832LL) = "*XMoveThreshold";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 848LL) = 212;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 852LL) = 148;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 844LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 840LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 856LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 860LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 864LL) = "*YMoveThreshold";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 880LL) = 216;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 884LL) = 152;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 876LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 872LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 888LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 892LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 896LL) = "*XMoveUnit";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 912LL) = 220;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 916LL) = 156;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 908LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 904LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 920LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 924LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 928LL) = "*YMoveUnit";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 944LL) = 224;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 948LL) = 160;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 940LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 936LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 952LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 956LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 960LL) = "*LineSpacingMoveUnit";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 976LL) = 228;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 980LL) = 164;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 972LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 968LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 984LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 988LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 992LL) = "*ChangeColorModeOnPage?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1008LL) = 232;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1012LL) = 168;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1004LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1000LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1016LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1020LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1024LL) = "*MagentaInCyanDye";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1040LL) = 240;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1044LL) = 172;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1036LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1032LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1048LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1052LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1056LL) = "*YellowInCyanDye";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1072LL) = 244;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1076LL) = 176;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1068LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1064LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1080LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1084LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1088LL) = "*CyanInMagentaDye";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1104LL) = 248;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1108LL) = 180;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1100LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1096LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1112LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1116LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1120LL) = "*YellowInMagentaDye";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1136LL) = 252;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1140LL) = 184;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1132LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1128LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1144LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1148LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1152LL) = "*CyanInYellowDye";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1168LL) = 256;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1172LL) = 188;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1164LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1160LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1176LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1180LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1184LL) = "*MagentaInYellowDye";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1200LL) = 260;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1204LL) = 192;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1196LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1192LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1208LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1212LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1216LL) = "*MaxNumPalettes";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1232LL) = 276;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1236LL) = 200;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1228LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1224LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1240LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1244LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1248LL) = "*OutputDataFormat";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1264LL) = 108;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1268LL) = 212;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1260LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1256LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1272LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1276LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1280LL) = "*OptimizeLeftBound?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1296LL) = 288;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1300LL) = 216;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1292LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1288LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1304LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1308LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1312LL) = "*StripBlanks";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1328LL) = 292;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1332LL) = 220;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1324LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1320LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1336LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1340LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1344LL) = "*RasterSendAllData?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1360LL) = 304;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1364LL) = 224;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1356LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1352LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1368LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1372LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1376LL) = "*CursorXAfterSendBlockData";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1392LL) = 316;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1396LL) = 228;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1388LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1384LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1400LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1404LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1408LL) = "*CursorYAfterSendBlockData";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1424LL) = 320;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1428LL) = 232;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1420LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1416LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1432LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1436LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1440LL) = "*MirrorRasterByte?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1456LL) = 324;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1460LL) = 252;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1452LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1448LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1464LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1468LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1472LL) = "*MirrorRasterPage?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1488LL) = 328;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1492LL) = 256;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1484LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1480LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1496LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1500LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1504LL) = "*PreAnalysisOptions";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1520LL) = 332;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1524LL) = 260;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1516LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1512LL) = bIsOnVistaAndAbove() != 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1528LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1532LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1536LL) = "*UseExpColorSelectCmd?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1552LL) = 264;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1556LL) = 236;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1548LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1544LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1560LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1564LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1568LL) = "*MoveToX0BeforeSetColor?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1584LL) = 268;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1588LL) = 240;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1580LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1576LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1592LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1596LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1600LL) = "*EnableGDIColorMapping?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1616LL) = 272;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1620LL) = 196;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1612LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1608LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1624LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1628LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1632LL) = "*SendMultipleRows?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1648LL) = 308;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1652LL) = 244;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1644LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1640LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1656LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1660LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1664LL) = "*DeviceFonts";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1680LL) = 336;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1684LL) = 264;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1676LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1672LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1688LL) = 40960;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1692LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1696LL) = "*DefaultFont";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1712LL) = 340;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1716LL) = 268;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1708LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1704LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1720LL) = 0x2000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1724LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1728LL) = "*MaxFontUsePerPage";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1744LL) = 356;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1748LL) = 272;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1740LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1736LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1752LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1756LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1760LL) = "*DefaultCTT";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1776LL) = 352;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1780LL) = 276;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1772LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1768LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1784LL) = 0x20000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1788LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1792LL) = "*LookaheadRegion";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1808LL) = 192;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1812LL) = 280;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1804LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1800LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1816LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1820LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1824LL) = "*TextYOffset";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1840LL) = 360;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1844LL) = 284;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1836LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1832LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1848LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1852LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1856LL) = "*CharPosition";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1872LL) = 364;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1876LL) = 288;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1868LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1864LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1880LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1884LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1888LL) = "*TTFSEnabled?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1904LL) = 344;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1908LL) = 292;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1900LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1896LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1912LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1916LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1920LL) = "*MinFontID";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1936LL) = 372;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1940LL) = 296;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1932LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1928LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1944LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1948LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1952LL) = "*MaxFontID";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1968LL) = 376;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1972LL) = 300;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1964LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1960LL) = 0xFFFF;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1976LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1980LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1984LL) = "*MaxNumDownFonts";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2000LL) = 380;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2004LL) = 304;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1996LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1992LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2008LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2012LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2016LL) = "*DLSymbolSet";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2032LL) = 392;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2036LL) = 308;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2028LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2024LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2040LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2044LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2048LL) = "*MinGlyphID";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2064LL) = 384;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2068LL) = 312;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2060LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2056LL) = 32;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2072LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2076LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2080LL) = "*MaxGlyphID";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2096LL) = 388;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2100LL) = 316;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2092LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2088LL) = 255;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2104LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2108LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2112LL) = "*DiffFontsPerByteMode?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2128LL) = 368;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2132LL) = 324;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2124LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2120LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2136LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2140LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2144LL) = "*CursorXAfterRectFill";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2160LL) = 408;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2164LL) = 328;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2156LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2152LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2168LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2172LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2176LL) = "*CursorYAfterRectFill";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2192LL) = 412;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2196LL) = 332;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2188LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2184LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2200LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2204LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2208LL) = "*MinGrayFill";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2224LL) = 416;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2228LL) = 336;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2220LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2216LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2232LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2236LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2240LL) = "*MaxGrayFill";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2256LL) = 420;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2260LL) = 340;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2252LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2248LL) = 100;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2264LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2268LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2272LL) = "*UseBMPFontCompression?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2288LL) = 432;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2292LL) = 352;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2284LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2280LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2296LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2300LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2304LL) = "*UseMode5Compression?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2320LL) = 436;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2324LL) = 356;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2316LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2312LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2328LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2332LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2336LL) = "*UseImageForHatchBrush?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2352LL) = 444;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2356LL) = 360;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2348LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2344LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2360LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2364LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2368LL) = "*UseHPGLPolylineEncoding?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2384LL) = 440;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2388LL) = 348;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2380LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2376LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2392LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2396LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2400LL) = "*XPSLandscapeMode";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2416LL) = 448;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2420LL) = 364;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2412LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2408LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2424LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2428LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2444LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2464LL) = "*MaxMultipleRowBytes";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2480LL) = 312;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2484LL) = 248;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2476LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2472LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2488LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2492LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2496LL) = "*TextHalftoneThreshold";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2512LL) = 424;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2516LL) = 344;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2508LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2504LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2520LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2524LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2528LL) = "*FontFormat";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2544LL) = 400;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2548LL) = 320;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2540LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2536LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2552LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2556LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2572LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2592LL) = "*ResourceDLL";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2608LL) = 80;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2612LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2604LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2600LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2616LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2620LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2624LL) = "*BidiQueryFile";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2640LL) = 32;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2644LL) = 312;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2636LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2632LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2648LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2652LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2656LL) = "*rcPersonalityID";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2672LL) = 76;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2676LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2668LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2664LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2680LL) = 16400;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2684LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2688LL) = "*Personality";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2704LL) = 72;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2708LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2700LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2696LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2712LL) = 6;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2716LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2720LL) = "*PrintSchemaPrivateNamespaceURI";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2736LL) = 28;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2740LL) = 184;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2732LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2728LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2744LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2748LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2752LL) = "*MaxCopies";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2768LL) = 88;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2772LL) = 60;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2764LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2760LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2776LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2780LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2784LL) = "*DefaultCopies";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2800LL) = 92;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2804LL) = 64;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2796LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2792LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2808LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2812LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2816LL) = "*rcPrinterIconID";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2832LL) = 100;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2836LL) = 148;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2828LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2824LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2840LL) = 0x10000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2844LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2848LL) = "*FontCartSlots";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2864LL) = 96;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2868LL) = 152;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2860LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2856LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2872LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2876LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2880LL) = "*HelpFile";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2896LL) = 104;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2900LL) = 168;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2892LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2888LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2904LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2908LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2912LL) = "*MasterUnits";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2928LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2932LL) = 172;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2924LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2920LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2936LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2940LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2944LL) = "*PrintRate";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2960LL) = 144;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2964LL) = 120;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2956LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2952LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2968LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2972LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2976LL) = "*PrintRateUnit";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2992LL) = 148;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2996LL) = 124;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2988LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2984LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3000LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3004LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3008LL) = "*PrintRatePPM";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3024LL) = 152;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3028LL) = 128;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3020LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3016LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3032LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3036LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3040LL) = "*LETTER_SIZE_EXISTS?  synthesized";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3056LL) = 456;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3060LL) = 140;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3052LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3048LL) = 512;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3064LL) = 0x40000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3068LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3072LL) = "*A4_SIZE_EXISTS?  synthesized";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3088LL) = 460;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3092LL) = 140;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3084LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3080LL) = 1024;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3096LL) = 0x40000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3100LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3116LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3136LL) = "*OutputOrderReversed? (global)";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3152LL) = 156;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3156LL) = 140;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3148LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3144LL) = 256;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3160LL) = 0x40000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3164LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3168LL) = "*ReverseBandOrderForEvenPages?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3184LL) = 160;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3188LL) = 140;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3180LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3176LL) = 0x2000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3192LL) = 0x40000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3196LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3200LL) = "*ReverseBandOrder?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3216LL) = 164;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3220LL) = 140;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3212LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3208LL) = 0x4000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3224LL) = 0x40000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3228LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3232LL) = "*NoPunctuationCharSubstitute?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3248LL) = 168;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3252LL) = 140;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3244LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3240LL) = 0x8000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3256LL) = 0x40000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3260LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3264LL) = "*DraftQualitySettings";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3280LL) = 52;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3284LL) = 188;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3276LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3272LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3288LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3292LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3296LL) = "*BetterQualitySettings";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3312LL) = 56;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3316LL) = 192;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3308LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3304LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3320LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3324LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3328LL) = "*BestQualitySettings";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3344LL) = 60;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3348LL) = 196;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3340LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3336LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3352LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3356LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3360LL) = "*DefaultQuality";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3376LL) = 64;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3380LL) = 200;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3372LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3368LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3384LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3388LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3392LL) = "*ChangeColorModeOnDoc?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3408LL) = 236;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3412LL) = 180;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3404LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3400LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3416LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3420LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3424LL) = "PrintProcDuplexOptions";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3440LL) = 428;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3444LL) = 296;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3436LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3432LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3448LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3452LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3456LL) = "*IsXPSDriver?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3472LL) = 464;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3476LL) = 300;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3468LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3464LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3480LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3484LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3488LL) = "*JobPasscodeMinLength";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3504LL) = 468;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3508LL) = 304;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3500LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3496LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3512LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3516LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3520LL) = "*JobPasscodeMaxLength";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3536LL) = 472;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3540LL) = 308;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3532LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3528LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3544LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3548LL) = 0;
    return 111;
  }
  return result;
}

```

## disassembly

```asm
0x180029010  push    rbx
0x180029012  sub     rsp, 30h
0x180029016  mov     rbx, rcx
0x180029019  mov     edx, 1C20h; uBytes
0x18002901e  xor     ecx, ecx; uFlags
0x180029020  call    cs:__imp_LocalAlloc
0x180029027  nop     dword ptr [rax+rax+00h]
0x18002902c  mov     [rbx+0B0h], rax
0x180029033  test    rax, rax
0x180029036  jz      loc_18002C11B
0x18002903c  mov     [rsp+38h+arg_0], rbp
0x180029041  lea     rcx, aGpdspecversion; "*GPDSpecVersion"
0x180029048  mov     [rax], rcx
0x18002904b  lea     rcx, aGpdfileversion; "*GPDFileVersion"
0x180029052  mov     rax, [rbx+0B0h]
0x180029059  mov     [rsp+38h+arg_8], rsi
0x18002905e  mov     [rsp+38h+arg_10], rdi
0x180029063  mov     [rsp+38h+arg_18], r12
0x180029068  xor     r12d, r12d
0x18002906b  mov     [rax+10h], r12d
0x18002906f  mov     rax, [rbx+0B0h]
0x180029076  mov     [rsp+38h+var_10], r14
0x18002907b  mov     [rsp+38h+var_18], r15
0x180029080  lea     r15, aMasterunits_0; "*MasterUnits"
0x180029087  mov     [rax+14h], r12d
0x18002908b  mov     rax, [rbx+0B0h]
0x180029092  mov     dword ptr [rax+0Ch], 8
0x180029099  mov     rax, [rbx+0B0h]
0x1800290a0  mov     [rax+8], r12d
0x1800290a4  mov     rax, [rbx+0B0h]
0x1800290ab  mov     dword ptr [rax+18h], 9
0x1800290b2  mov     rax, [rbx+0B0h]
0x1800290b9  mov     [rax+1Ch], r12d
0x1800290bd  mov     rax, [rbx+0B0h]
0x1800290c4  mov     [rax+20h], rcx
0x1800290c8  lea     rcx, aGpdfilename; "*GPDFileName"
0x1800290cf  mov     rax, [rbx+0B0h]
0x1800290d6  mov     dword ptr [rax+30h], 10h
0x1800290dd  mov     rax, [rbx+0B0h]
0x1800290e4  mov     dword ptr [rax+34h], 8
0x1800290eb  mov     rax, [rbx+0B0h]
0x1800290f2  mov     dword ptr [rax+2Ch], 8
0x1800290f9  mov     rax, [rbx+0B0h]
0x180029100  mov     [rax+28h], r12d
0x180029104  mov     rax, [rbx+0B0h]
0x18002910b  mov     dword ptr [rax+38h], 8
0x180029112  mov     rax, [rbx+0B0h]
0x180029119  mov     [rax+3Ch], r12d
0x18002911d  mov     rax, [rbx+0B0h]
0x180029124  mov     [rax+40h], rcx
0x180029128  lea     rcx, aModelname; "*ModelName"
0x18002912f  mov     rax, [rbx+0B0h]
0x180029136  mov     dword ptr [rax+50h], 14h
0x18002913d  mov     rax, [rbx+0B0h]
0x180029144  mov     dword ptr [rax+54h], 20h ; ' '
0x18002914b  mov     rax, [rbx+0B0h]
0x180029152  mov     dword ptr [rax+4Ch], 8
0x180029159  mov     rax, [rbx+0B0h]
0x180029160  mov     [rax+48h], r12d
0x180029164  mov     rax, [rbx+0B0h]
0x18002916b  mov     dword ptr [rax+58h], 8
0x180029172  mov     rax, [rbx+0B0h]
0x180029179  mov     [rax+5Ch], r12d
0x18002917d  mov     rax, [rbx+0B0h]
0x180029184  mov     [rax+60h], r15
0x180029188  mov     rax, [rbx+0B0h]
0x18002918f  mov     dword ptr [rax+70h], 4
0x180029196  mov     rax, [rbx+0B0h]
0x18002919d  mov     dword ptr [rax+74h], 10h
0x1800291a4  mov     rax, [rbx+0B0h]
0x1800291ab  mov     dword ptr [rax+6Ch], 8
0x1800291b2  mov     rax, [rbx+0B0h]
0x1800291b9  mov     [rax+68h], r12d
0x1800291bd  mov     rax, [rbx+0B0h]
0x1800291c4  mov     dword ptr [rax+78h], 1
0x1800291cb  mov     rax, [rbx+0B0h]
0x1800291d2  mov     [rax+7Ch], r12d
0x1800291d6  mov     rax, [rbx+0B0h]
0x1800291dd  mov     [rax+80h], rcx
0x1800291e4  mov     rax, [rbx+0B0h]
0x1800291eb  mov     dword ptr [rax+90h], 8
0x1800291f5  mov     rax, [rbx+0B0h]
0x1800291fc  mov     dword ptr [rax+94h], 18h
0x180029206  mov     rax, [rbx+0B0h]
0x18002920d  mov     dword ptr [rax+8Ch], 8
0x180029217  mov     rax, [rbx+0B0h]
0x18002921e  mov     [rax+88h], r12d
0x180029225  mov     rax, [rbx+0B0h]
0x18002922c  mov     dword ptr [rax+98h], 9
0x180029236  mov     rax, [rbx+0B0h]
0x18002923d  mov     [rax+9Ch], r12d
0x180029244  mov     rax, [rbx+0B0h]
0x18002924b  lea     rcx, aPrintertype; "*PrinterType"
0x180029252  lea     rdi, aResourcedll_0; "*ResourceDLL"
0x180029259  lea     rbp, aMaxcopies; "*MaxCopies"
0x180029260  lea     rsi, aDefaultcopies; "*DefaultCopies"
0x180029267  mov     [rax+0A0h], rcx
0x18002926e  lea     r14, aFontcartslots; "*FontCartSlots"
0x180029275  mov     rax, [rbx+0B0h]
0x18002927c  lea     rcx, aOemcustomdata; "*OEMCustomData"
0x180029283  mov     dword ptr [rax+0B0h], 44h ; 'D'
0x18002928d  mov     rax, [rbx+0B0h]
0x180029294  mov     dword ptr [rax+0B4h], 28h ; '('
0x18002929e  mov     rax, [rbx+0B0h]
0x1800292a5  mov     dword ptr [rax+0ACh], 4
0x1800292af  mov     rax, [rbx+0B0h]
0x1800292b6  mov     [rax+0A8h], r12d
0x1800292bd  mov     rax, [rbx+0B0h]
0x1800292c4  mov     dword ptr [rax+0B8h], 1
0x1800292ce  mov     rax, [rbx+0B0h]
0x1800292d5  mov     [rax+0BCh], r12d
0x1800292dc  mov     rax, [rbx+0B0h]
0x1800292e3  mov     [rax+0C0h], rdi
0x1800292ea  mov     rax, [rbx+0B0h]
0x1800292f1  mov     dword ptr [rax+0D0h], 50h ; 'P'
0x1800292fb  mov     rax, [rbx+0B0h]
0x180029302  mov     dword ptr [rax+0D4h], 38h ; '8'
0x18002930c  mov     rax, [rbx+0B0h]
0x180029313  mov     dword ptr [rax+0CCh], 8
0x18002931d  mov     rax, [rbx+0B0h]
0x180029324  mov     [rax+0C8h], r12d
0x18002932b  mov     rax, [rbx+0B0h]
0x180029332  mov     dword ptr [rax+0D8h], 8
0x18002933c  mov     rax, [rbx+0B0h]
0x180029343  mov     [rax+0DCh], r12d
0x18002934a  mov     rax, [rbx+0B0h]
0x180029351  mov     [rax+0E0h], rbp
0x180029358  mov     rax, [rbx+0B0h]
0x18002935f  mov     dword ptr [rax+0F0h], 58h ; 'X'
0x180029369  mov     rax, [rbx+0B0h]
0x180029370  mov     dword ptr [rax+0F4h], 40h ; '@'
0x18002937a  mov     rax, [rbx+0B0h]
0x180029381  mov     dword ptr [rax+0ECh], 4
0x18002938b  mov     rax, [rbx+0B0h]
0x180029392  mov     dword ptr [rax+0E8h], 1
0x18002939c  mov     rax, [rbx+0B0h]
0x1800293a3  mov     [rax+0F8h], r12d
0x1800293aa  mov     rax, [rbx+0B0h]
0x1800293b1  mov     [rax+0FCh], r12d
0x1800293b8  mov     rax, [rbx+0B0h]
0x1800293bf  mov     [rax+100h], rsi
0x1800293c6  mov     rax, [rbx+0B0h]
0x1800293cd  mov     dword ptr [rax+110h], 5Ch ; '\'
0x1800293d7  mov     rax, [rbx+0B0h]
0x1800293de  mov     dword ptr [rax+114h], 44h ; 'D'
0x1800293e8  mov     rax, [rbx+0B0h]
0x1800293ef  mov     dword ptr [rax+10Ch], 4
0x1800293f9  mov     rax, [rbx+0B0h]
0x180029400  mov     dword ptr [rax+108h], 1
0x18002940a  mov     rax, [rbx+0B0h]
0x180029411  mov     [rax+118h], r12d
0x180029418  mov     rax, [rbx+0B0h]
0x18002941f  mov     [rax+11Ch], r12d
0x180029426  mov     rax, [rbx+0B0h]
0x18002942d  mov     [rax+120h], r14
0x180029434  mov     rax, [rbx+0B0h]
0x18002943b  mov     dword ptr [rax+130h], 60h ; '`'
0x180029445  mov     rax, [rbx+0B0h]
0x18002944c  mov     dword ptr [rax+134h], 48h ; 'H'
0x180029456  mov     rax, [rbx+0B0h]
0x18002945d  mov     dword ptr [rax+12Ch], 4
0x180029467  mov     rax, [rbx+0B0h]
0x18002946e  mov     [rax+128h], r12d
0x180029475  mov     rax, [rbx+0B0h]
0x18002947c  mov     [rax+138h], r12d
0x180029483  mov     rax, [rbx+0B0h]
0x18002948a  mov     [rax+13Ch], r12d
0x180029491  mov     rax, [rbx+0B0h]
0x180029498  mov     [rax+140h], rcx
0x18002949f  mov     rax, [rbx+0B0h]
0x1800294a6  mov     dword ptr [rax+150h], 18h
0x1800294b0  mov     rax, [rbx+0B0h]
0x1800294b7  mov     dword ptr [rax+154h], 50h ; 'P'
0x1800294c1  mov     rax, [rbx+0B0h]
0x1800294c8  mov     dword ptr [rax+14Ch], 8
0x1800294d2  mov     rax, [rbx+0B0h]
0x1800294d9  mov     [rax+148h], r12d
0x1800294e0  mov     rax, [rbx+0B0h]
0x1800294e7  mov     dword ptr [rax+158h], 8
0x1800294f1  mov     rax, [rbx+0B0h]
0x1800294f8  mov     [rax+15Ch], r12d
0x1800294ff  mov     rax, [rbx+0B0h]
0x180029506  mov     [rax+160h], rcx
0x18002950d  lea     rcx, aRotatecoordina; "*RotateCoordinate?"
0x180029514  mov     rax, [rbx+0B0h]
0x18002951b  mov     dword ptr [rax+170h], 18h
0x180029525  mov     rax, [rbx+0B0h]
0x18002952c  mov     dword ptr [rax+174h], 58h ; 'X'
0x180029536  mov     rax, [rbx+0B0h]
0x18002953d  mov     dword ptr [rax+16Ch], 4
0x180029547  mov     rax, [rbx+0B0h]
0x18002954e  mov     [rax+168h], r12d
0x180029555  mov     rax, [rbx+0B0h]
0x18002955c  mov     dword ptr [rax+178h], 1000h
0x180029566  mov     rax, [rbx+0B0h]
0x18002956d  mov     [rax+17Ch], r12d
0x180029574  mov     rax, [rbx+0B0h]
0x18002957b  mov     [rax+180h], rcx
0x180029582  lea     rcx, aRotateraster; "*RotateRaster?"
0x180029589  mov     rax, [rbx+0B0h]
0x180029590  mov     dword ptr [rax+190h], 74h ; 't'
0x18002959a  mov     rax, [rbx+0B0h]
0x1800295a1  mov     dword ptr [rax+194h], 5Ch ; '\'
0x1800295ab  mov     rax, [rbx+0B0h]
0x1800295b2  mov     dword ptr [rax+18Ch], 4
0x1800295bc  mov     rax, [rbx+0B0h]
0x1800295c3  mov     [rax+188h], r12d
0x1800295ca  mov     rax, [rbx+0B0h]
0x1800295d1  mov     [rax+198h], r12d
0x1800295d8  mov     rax, [rbx+0B0h]
0x1800295df  mov     [rax+19Ch], r12d
0x1800295e6  mov     rax, [rbx+0B0h]
0x1800295ed  mov     [rax+1A0h], rcx
0x1800295f4  lea     rcx, aTextcaps_0; "*TextCaps"
0x1800295fb  mov     rax, [rbx+0B0h]
0x180029602  mov     dword ptr [rax+1B0h], 7Ch ; '|'
0x18002960c  mov     rax, [rbx+0B0h]
0x180029613  mov     dword ptr [rax+1B4h], 60h ; '`'
0x18002961d  mov     rax, [rbx+0B0h]
0x180029624  mov     dword ptr [rax+1ACh], 4
0x18002962e  mov     rax, [rbx+0B0h]
0x180029635  mov     [rax+1A8h], r12d
0x18002963c  mov     rax, [rbx+0B0h]
0x180029643  mov     [rax+1B8h], r12d
0x18002964a  mov     rax, [rbx+0B0h]
0x180029651  mov     [rax+1BCh], r12d
0x180029658  mov     rax, [rbx+0B0h]
0x18002965f  mov     [rax+1C0h], rcx
0x180029666  lea     rcx, aRotatefont; "*RotateFont?"
0x18002966d  mov     rax, [rbx+0B0h]
0x180029674  mov     dword ptr [rax+1D0h], 80h
0x18002967e  mov     rax, [rbx+0B0h]
0x180029685  mov     dword ptr [rax+1D4h], 64h ; 'd'
0x18002968f  mov     rax, [rbx+0B0h]
0x180029696  mov     dword ptr [rax+1CCh], 4
0x1800296a0  mov     rax, [rbx+0B0h]
0x1800296a7  mov     dword ptr [rax+1C8h], 0FFFFFFFFh
0x1800296b1  mov     rax, [rbx+0B0h]
0x1800296b8  mov     [rax+1D8h], r12d
0x1800296bf  mov     rax, [rbx+0B0h]
0x1800296c6  mov     [rax+1DCh], r12d
0x1800296cd  mov     rax, [rbx+0B0h]
0x1800296d4  mov     [rax+1E0h], rcx
0x1800296db  mov     rax, [rbx+0B0h]
0x1800296e2  mov     dword ptr [rax+1F0h], 84h
0x1800296ec  mov     rax, [rbx+0B0h]
0x1800296f3  mov     dword ptr [rax+1F4h], 68h ; 'h'
0x1800296fd  mov     rax, [rbx+0B0h]
0x180029704  mov     dword ptr [rax+1ECh], 4
0x18002970e  mov     rax, [rbx+0B0h]
0x180029715  mov     [rax+1E8h], r12d
0x18002971c  mov     rax, [rbx+0B0h]
0x180029723  mov     [rax+1F8h], r12d
0x18002972a  mov     rax, [rbx+0B0h]
0x180029731  lea     rcx, aMemoryusage; "*MemoryUsage"
0x180029738  mov     [rax+1FCh], r12d
0x18002973f  mov     rax, [rbx+0B0h]
0x180029746  mov     [rax+200h], rcx
0x18002974d  lea     rcx, aReselectfont; "*ReselectFont"
0x180029754  mov     rax, [rbx+0B0h]
0x18002975b  mov     dword ptr [rax+210h], 88h
0x180029765  mov     rax, [rbx+0B0h]
0x18002976c  mov     dword ptr [rax+214h], 6Ch ; 'l'
0x180029776  mov     rax, [rbx+0B0h]
0x18002977d  mov     dword ptr [rax+20Ch], 4
0x180029787  mov     rax, [rbx+0B0h]
0x18002978e  mov     dword ptr [rax+208h], 0FFFFFFFFh
0x180029798  mov     rax, [rbx+0B0h]
0x18002979f  mov     [rax+218h], r12d
0x1800297a6  mov     rax, [rbx+0B0h]
0x1800297ad  mov     [rax+21Ch], r12d
0x1800297b4  mov     rax, [rbx+0B0h]
0x1800297bb  mov     [rax+220h], rcx
0x1800297c2  lea     rcx, aOemprintingcal; "*OEMPrintingCallbacks"
0x1800297c9  mov     rax, [rbx+0B0h]
0x1800297d0  mov     dword ptr [rax+230h], 8Ch
0x1800297da  mov     rax, [rbx+0B0h]
0x1800297e1  mov     dword ptr [rax+234h], 70h ; 'p'
0x1800297eb  mov     rax, [rbx+0B0h]
0x1800297f2  mov     dword ptr [rax+22Ch], 4
0x1800297fc  mov     rax, [rbx+0B0h]
0x180029803  mov     dword ptr [rax+228h], 0FFFFFFFFh
0x18002980d  mov     rax, [rbx+0B0h]
0x180029814  mov     [rax+238h], r12d
0x18002981b  mov     rax, [rbx+0B0h]
0x180029822  mov     [rax+23Ch], r12d
0x180029829  mov     rax, [rbx+0B0h]
0x180029830  mov     [rax+240h], rcx
0x180029837  lea     rcx, aCursorxaftercr; "*CursorXAfterCR"
0x18002983e  mov     rax, [rbx+0B0h]
0x180029845  mov     dword ptr [rax+250h], 0ACh
0x18002984f  mov     rax, [rbx+0B0h]
0x180029856  mov     dword ptr [rax+254h], 74h ; 't'
0x180029860  mov     rax, [rbx+0B0h]
0x180029867  mov     dword ptr [rax+24Ch], 4
0x180029871  mov     rax, [rbx+0B0h]
0x180029878  mov     dword ptr [rax+248h], 0FFFFFFFFh
0x180029882  mov     rax, [rbx+0B0h]
0x180029889  mov     [rax+258h], r12d
0x180029890  mov     rax, [rbx+0B0h]
  ... truncated ...
```
